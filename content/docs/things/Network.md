+++
title = "Network"
weight = 3
+++

 I have a 10 gigabit internal network and NVMe drives to support the speed, which gives me data transfers between my PC and server at over 1 Gigabyte per second. It's also fast for [Steam network transfers](https://help.steampowered.com/en/faqs/view/46BD-6BA8-B012-CE43), but they use some compression or internal cap that prevents it from maxing out the network speed. Real world transfer is around 2-3 gigabit.

This tool supports diagrams, how neat is that?
```mermaid
graph TD;
GF[1G internet<br><a href='https://fiber.google.com/'>Google Fiber</a>]-->UDMP

UDMP[<a href='https://store.ui.com/us/en/products/udm-pro'>Unifi Dream Machine Pro</a>]-->A[Rack Switch<br><a href='https://www.nicgiga.com/collections/10g-switch/products/8-port-10g-ethernet-switch'>8x10G SFP</a>]

A-->Z[<a href='../Server'>Server</a>]

A-->B[Livingroom Switch <a href='https://www.amazon.com/dp/B09LNLMH9Y'><br>2x10G 4x2.5G RJ45</a>]

B-->C[Office Switch<br><a href='https://www.nicgiga.com/collections/10g-switch/products/5-port-10g-ethernet-switch-unmanaged-with-5x-10gb-base-t-rj45-ports-nicgiga-10gbps-network-switch-easy-for-10g-nas-pc-wifi7-router-10g-adapter-nic-desktop-or-19-inch-rack-mount-plug-and-play'>5x10G RJ45</a>]

B-->D[WiFi 7 WAP<br><a href='https://store.ui.com/us/en/category/all-wifi/products/u7-pro'>Unifi U7 Pro</a>]

C-->Y[<a href='../PC'>PC 1</a>]
C-->X[PC 2]
```
