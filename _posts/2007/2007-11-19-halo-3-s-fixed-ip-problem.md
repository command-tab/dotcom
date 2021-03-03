---
layout: post
title: Halo 3's Fixed IP Problem
---
Ever since opening Halo 3 and hopping on Xbox Live with it, it's been complaining about my router's NAT settings.  Apparently, it needs certain ports open to connect to other gamers.  Tonight, I finally set out to get it working properly, but came up short.

After first doing a little research and discovering that Xbox Live uses TCP and UDP port 3074 and UDP port 88 (largely UDP port 3047, as indicated by my Ethereal packet dumps), I thought I could get away with forwarding those ports straight to my Xbox 360.  Since my console was set to automatically lease an IP address from my router, it would quite probably get a different IP each time it boots up, thus "breaking" my carefully forwarded ports.  The obvious solution is to choose a fixed IP address in the Xbox Dashboard.  Once the IP is set statically and the appropriate ports are forwarded, all seems to be well, except for one minor hangup...

If you boot directly to the Halo 3 disc with with a fixed IP address, the network connection never links up before executing the game.  Halo 3 runs, then refuses to connect to Xbox Live.  I have to exit the game, go back to the Xbox Dashboard, Sign In to Xbox Live, then re-launch Halo to get it to go online.  It couldn't be a more roundabout way, but it seems that's the only answer aside from enabling uPNP on the router, which I'll never do for security reasons.  I doubt my DD-WRT powered WRT54GL router is "Microsoft Certified," but the problem seems to lie with the Xbox 360 or Halo 3, as it won't even acknowledge the presence of an Ethernet cable until the Xbox Dashboard launches.  Weird.

**Update:**Here's one solution: Open the DD-WRT settings, go to Administration, Services, then the DHCP Server grouping and set a static lease for the Xbox 360's MAC address. Set the Xbox 360 back to Automatic IP address leasing, and the router will assign a fixed IP based on the console's MAC, ensuring it's the same every time, without the Xbox having to be set to static.
