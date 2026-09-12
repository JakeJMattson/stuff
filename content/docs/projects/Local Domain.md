+++
title = "Local Domain"
+++

With so many services running on my home network, it becomes cumbersome to remember all the IPs and ports to access them. It would be more convenient to be able to easily access them with a browser search instead of maintaining a massive list of bookmarks.

## Execution

My existing reverse proxy setup was using [SWAG](https://github.com/linuxserver/docker-swag) (Nginx), which made this task feel impossible with the amount of configuration ahead of me. I needed something with a much simpler config, which led me to [Caddy](https://caddyserver.com/). Below is a complete example that points to my [Local Wikipedia]({{< relref "docs/projects/Local Wikipedia" >}}). This pattern was easily copied for all my local services.

```
wiki.jake.lan {
    reverse_proxy 192.168.1.123:8771
    tls internal
}
```

With Caddy running on a dedicated IP, we now need to point browser requests for our domain pattern to that IP. Since I already control my local DNS with [AdGuard](https://adguard.com/en/welcome.html), this is straightforward. I created a DNS rewrite for `*.jake.lan -> [caddy IP]`, then Caddy handles the redirect for each service. As a bonus, I get local HTTPS for everything, which I used to support a [vaultwarden](https://github.com/dani-garcia/vaultwarden) setup.

## Usage

Visiting `https://wiki.jake.lan` now connects me to my local Wikipedia running on my server. No IP or port knowledge required. 

To make it even more convenient, I configured "site search" in my browser. This allows a hotkey to make custom search queries for a specific site. By setting up `https://%s.jake.lan` I can now reach any of my services by activating this shortcut and just typing the name of the service.