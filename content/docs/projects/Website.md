+++
title = "Website"
+++

This website is acting more like a blog than a code project, so I didn't want to actually make a website. I set out to find a static site generator which so I could develop it just by writing some simple text. 
## Execution

I discovered [Hugo](https://gohugo.io/) which lets me create the entire website in markdown. I created the [repository](https://github.com/JakeJMattson/stuff) on GitHub, and chose to deploy it with [GitHub Pages](https://pages.github.com/) since it's free and built for static content. This has an added bonus of not exposing my home IP and I don't have to worry about uptime.

After the initial setup, I added the [Lotus Docs Theme](https://lotusdocs.dev/docs/overview/). Since I had decided to host on GitHub Pages, I needed to create a GitHub Action for publishing which was provided by the Hugo Docs [template](https://gohugo.io/host-and-deploy/host-on-github-pages/). After a small change to support a custom theme, I was able to get it deployed automatically on push. This [workflow](https://github.com/JakeJMattson/stuff/blob/main/.github/workflows/hugo.yaml) is in my repo if you want to steal it.

The final touch was configuring the deployment to use my real domain. There are [GitHub Pages Docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages) that explain the process, but I just needed to setup a TXT record for verification and a 
`www` subdomain. 
## Usage

Now that all the deployment stuff is done, I write the text for these pages using [Obsidian](https://obsidian.md/) and deploy it locally with `hugo serve`. Once it looks good I push it to GitHub and the GitHub Action is executed which publishes the website in about a minute. 

