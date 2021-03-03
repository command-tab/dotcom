---
layout: post
title: How to Run Hamachi on Leopard
---
[A while back](/2006/08/13/hamachi-on-mac-os-x/) I detailed how to get Hamachi VPN running on Mac OS X, but times have changed, so here's how to go about it under Leopard. Again, it's a bit tricky, involving some Terminal work, but it's pretty straightforward as far as command-line software goes.

**Download and Install Tun/Tap**

Hamachi for Mac OS X depends on some other tunneling software, a Tun/Tap kernel extension which does the low-level work. [Download](http://tuntaposx.sourceforge.net/) the latest Tun/Tap package and install it.

**Download and Install Hamachi**

Next, [download](https://secure.logmein.com/products/hamachi/list.asp) the latest Hamachi for Mac OS X. Installation is a bit more complicated than the Tun/Tap drivers. Unzip the archive, and open up a Terminal window, and type `cd`, followed by a space. Don't press Return just yet... Instead, drop the Hamachi folder right into the Terminal window, which will insert the path to that folder after the prefix you just typed: `cd /Users/you/Downloads/hamachi-0.9.9.9-20-osx`. Press Return, and the Terminal's new working directory will be the Hamachi folder -- this is just a quick drag-and-drop shortcut to avoid typing out the path to a folder you already have available.

Once in the Hamachi folder, type `sudo ./install`. Enter your administrator password to perform the install.

Hamachi should now be installed, and you can initialize it for the first time by typing `hamachi-init`. This will generate public and private encryption keys in your Home folder, under `.hamachi/` (the initial dot makes the folder hidden in regular Finder windows). With both set-ups out of the way, it's time to start using Hamachi!

**Run Hamachi**

Configure Tun/Tap by typing `sudo ./usr/sbin/tuncfg`

Start up Hamachi by typing `hamachi start` followed by `hamachi login`.

At this point, you should be connected to the Hamachi service, but without a VPN for your computers to join. If you already have a network, or plan to join a trusted friend's network, you can easily join it by typing: `hamachi join SomeNetwork`.

Most likely, though, you'll need to create your own network: `hamachi create MyNetwork`

Now you should have a virtual network in place and can go online `hamachi go-online MyNetwork`.

To see other parties on the network, run `hamachi list`

If other computers are online, you're ready to connect to them with any higher-level software like iChat via Bonjour, the Finder's "Connect to Server" command, Safari, etc.

To log out of Hamachi and shut down VPN connections, run `hamachi stop`

For more information about how to use Hamachi, you can view its manual by running `hamachi -h`.
