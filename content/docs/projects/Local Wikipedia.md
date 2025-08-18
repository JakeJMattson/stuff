+++
title = "Local Wikipedia"
+++

With worldwide attacks on privacy such as intrusive ID laws, censorship, and talks of blocking VPNs, data is a feeling a lot more fragile these days. I've started being more mindful of this and have been archiving more data on my home server. I wanted a copy of Wikipedia and found that the distribution that I was interested in was just over 100 GB. 

## Execution

Wikipedia themselves has a page for [database downloads](https://en.wikipedia.org/wiki/Wikipedia:Database_download) and offline reading. The first recommendation is [Kiwix](https://en.wikipedia.org/wiki/Kiwix) which is an offline web browser for wiki content. This is available as a [docker container](https://github.com/kiwix/kiwix-tools/pkgs/container/kiwix-serve) that I run on my server. It started as a Wikipedia reader, but now has a [full library](https://library.kiwix.org/) of other content. 

Kiwix uses the [ZIM](https://en.wikipedia.org/wiki/ZIM_(file_format)) file format and hosts all of them for download on their [download page](https://download.kiwix.org/zim/wikipedia/). If you click any of these zims it will attempt to download over HTTP. Since these downloads may be massive, they recommend using a torrent instead. This saves their bandwidth verifies that your file is not corrupted during the download process.

Finding these torrents gave me a bit of trouble, but you can use the same download page to access them. If you right click on any zim entry, you can copy the link address which should give you the path to the zim. If you add `.torrent` to the end of it, it will download the torrent instead of the file directly. Since I wanted all English articles with pictures, this is my download link: <br>
https://download.kiwix.org/zim/wikipedia/wikipedia_en_all_maxi_2024-01.zim.torrent

## Usage

After downloading the content and setting up the Kiwix container, I can now browse a completely local version of Wikipedia hosted on my home server.