# Software

These are project ideas that are mostly just standing up services on my [Server]({{< relref "things/Server" >}})

{{% details title="Dynamic DNS" closed="false" %}}

My domain registrar offers dynamic DNS functionality. If my public IP changes, this service would update the IP target on my subdomains. Currently I am using [DuckDNS](https://www.duckdns.org/) for this, but it would be nice to have one less third party service.

{{% /details %}}
{{% details title="Personal Cloud" %}}

I setup [NextCloud](https://nextcloud.com/) locally but still need configure the proxy with a subdomain. I plan to share this with a few friends so they can store their Obsidian vaults there and sync them between devices. They also like share files between themselves, which NextCloud can also do.

{{% /details %}}
{{% details title="Self-hosted Google Docs" %}}

I want to be able to collaborate on documents hosted on my server. It seems like OnlyOffice is one way to go about it, there's a [NextCloud plugin](https://www.onlyoffice.com/office-for-nextcloud.aspx) that looks really nice. Will probably wrap this project into my personal cloud project.

{{% /details %}}
{{% details title="Remote Laptop VM" %}}

My laptop is super old so it would be cool to setup a virtual machine to share that with the laptop over RDP or something similar. I tried [KASM](https://kasmweb.com/) with Ubuntu so I could share my GPU with the container, but I got trapped in config land and couldn't get it to work cleanly.

{{% /details %}}
{{% details title="Docker VPN network" %}}

I want a way to share a VPN tunnel between a few of my services instead of setting it up manually every time, or looking for a version of a container with VPN support added onto it. My current idea is a docker container with OpenVPN on a docker network, then other containers can use that network. Seemingly things do not work easily like that, and I'd have to map the ports for each container through the VPN one which sucks.

{{% /details %}}
{{% details title="Tailscale for apps" %}}

Instead of using a reverse proxy and exposing more things, I should reduce my footprint and use [Tailscale](https://tailscale.com/) for apps where I'm the only user. Unraid has Tailscale integration natively but I deploy some of my services with docker-compose, so there's no cool UI button.

{{% /details %}}


