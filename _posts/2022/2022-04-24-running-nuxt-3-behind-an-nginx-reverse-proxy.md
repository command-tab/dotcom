---
layout: post
title: Running Nuxt 3 Behind an nginx Reverse Proxy
categories: docs
---
I was attempting to run [Nuxt 3](https://github.com/nuxt/framework) RC1 in development mode behind a local nginx reverse proxy, but ran into several issues. There are a number of reasons to run a development application server behind a [TLS-terminating reverse proxy](https://en.wikipedia.org/wiki/TLS_termination_proxy), including more closely mirroring a production setup, ensuring an application performs correctly when proxied, and gaining HTTPS support to enable use of  newer [HTTPS-only user-agent APIs](https://www.digicert.com/blog/https-only-features-in-browsers).

However, when nginx reverse proxies to the Nuxt server using a configuration like the following, the application will load correctly in the browser but [Vite](https://vitejs.dev) (bundled with Nuxt) will no longer be able connect to its backend websocket server to provide hot module replacement (HMR).

    location / {
        proxy_pass http://localhost:3000;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header Host $host;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }

To fix this, Vite needs to be made aware it's being reverse proxied, and nginx needs to pass through Vite's websocket connection.

In the Nuxt config (`nuxt.config.ts`), add the following Vite config:

    vite: {
      server: {
        hmr: {
          protocol: 'wss',
          clientPort: 443,
          path: 'hmr/'
        }
      }
    }

Vite will now use the secure websocket protocol over the same HTTPS port as the application, but it will request it at a new, distinct path.

In the nginx config, add a new `location` directive to match the configured Vite path (`/_nuxt` is always prepended), have it perform an HTTP Upgrade, and then reverse proxy to Vite's websocket server, which always listens on port 24678:

    location /_nuxt/hmr/ {
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "Upgrade";
        proxy_pass http://localhost:24678;
    }

After restarting the development server and nginx, Nuxt 3 and Vite HMR work great behind nginx, which now handles TLS termination and reverse proxying of HTTP and websocket traffic.

**Update 2023-09-28**

As of Nuxt 3.7.4, the `nuxt.config.ts` configuration [is unnecessary](https://github.com/nuxt/nuxt/issues/12003#issuecomment-1738373498), though having the following nginx config in place avoids a WebSocket error about the WebSocket host being undefined:

    location /_nuxt/ {
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
        proxy_pass http://localhost:3000;
    }

Note the differences from the above config -- the location path dropped `hmr/`, the Vite HMR port (`24678`) became the default Nuxt port (`3000`), and the `Host` header was also added (but the `Host` header is likely not critical for this scenario).
