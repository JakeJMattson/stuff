+++
title = "Network Ad Blocking"
+++

Ad blocking browsers and extensions are great for your local device, but why not spread the love to all the devices on your network.

## Execution

For this project I chose to use [AdGuard](https://adguard.com/en/welcome.html) running in docker on my Unraid server.
Using the template will create a new device with the `br0` network, giving it its own IP address on your network.
Now you can use that IP as a DNS server on your client devices or directly on your router.

A potential issue I saw with this implementation is in the event of a server outage. 
I wanted to create a backup system with faster startup, and chose to run a second AdGuard on a [Raspberry Pi Zero 2 W](https://www.raspberrypi.com/products/raspberry-pi-zero-2-w/).
This gives me a primary and secondary DNS option to provide in my router.

Managing two instances seemed annoying, so I also set up [AdGuardHome-Sync](https://github.com/bakito/adguardhome-sync) to sync my configuration settings between my server and pi installations.
After some networking roadblocks, everything works great and I can see all the queries and blocked trackers in the dashboard.

## Roadblocks

My first issue was on my Dream Machine Pro router. It comes with built-in functionality that performs a similar role to AdGuard. This was causing all of my requests in AdGuard to originate from my router.
I was able to fix this by disabling the existing ad blocking and content filtering options.

The second issue was that AdGuardHome-Sync was not able to connect to the AdGuard instance. 
I found out this was a feature of the `br0` interface. I was then able to go into the docker settings in Unraid and allow "Host access to custom networks".
This fixed my connection issue and sync was successful.

## Usage

From the network client perspective, there is no usage step. Everything runs seamlessly in the background blocking ads, trackers, and malicious sites.