---
title: "Azure Static Web Apps Redirects"
date: "2020-12-22T22:01:00.000Z"
template: "post"
draft: false
category: "Azure Static Web Apps"
tags:
  - "Azure DevOps"
  - "Azure Cloud"
description: "Azure Static Web Apps Redirects and the benefits and limitations"
socialImage: "/media/default-social-image.jpg"
---


# Azure Static Web Apps Redirects
[Azure Static Web Apps](https://docs.microsoft.com/en-us/azure/static-web-apps/) is my favorite solution for simple websites. They are very fast, simple to setup, and are extremely cheap. You can also use Azure Functions to support [API endpoints](https://docs.microsoft.com/en-us/azure/static-web-apps/apis) if you're building a SPA, or need to add some functionality to your website.

One of the major limitations that I hope will be resolved in the future is the ability to serve a site at a domains's root or apex (ie https://jbarrera.io). There are [workarounds](https://burkeholland.github.io/posts/static-app-root-domain) to support this, but for now it's not available out of the box. I mention this, because I would like to redirect http(s)://jbarrera.io to http(s)://www.jbarrera.io. I was curious if I could have another vanity domain point at this current website, and so I started playing with redirects on a different website.

By creating a *routes.json* in your Azure Static Web App, you can configure routes and give it a number of options. To test if I could redirect from another domain to my website I created a new website. In my solution, I created an *index.html* (required for build/release workflows in the default solution) and added the following to my *routes.json*:

    {
        "routes": [
            {
                "route": "/*",
                "serve": "https://www.jbarrera.io",
                "statusCode": 302    
            }
        ]
    }

The nice thing is that I was able to redirect all traffic, with the 302 HTTP Status code to my website. I could also bind this to multiple domains, though I couldn't find the maximum number that you could bind to. The main limitation would be that you can't use the root domain if that's what was typed in explicitly.