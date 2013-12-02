---
layout: project
title: Default Platform
subtitle: The Search and Solution for Today
categories:
- project
tags:
- paas
- iaas
---

## The Need: Productivity and Standardization
I have tried various PaaS providers with great results. PaaS continues to improve over time and I think they are quickly moving from an 80% solution to a 90% percent solution. However, I seem to spend a lot of time in the 10% that is not adequately addressed by PaaS.

## Outlier Support
PaaS solutions tend to be an all-or-nothing proposition (almost by definition) so I’m usually stuck with custom options. For the applications that I develop, deploy, and operate, _scale_ is not a significant issue. We’re talking B2B situations without a lot of unknowns. Even so, I try to leave room for the unexpected.

For example, I’m very intentional about decoupling the database layer. This leaves room for DBaaS solutions such as [mongolab](https://mongolab.com/welcome/). It also leaves room for me to do whatever is necessary at the database layer.

As another example, take reverse proxies. For awhile most PaaS providers forced you into specific proxy solutions - forcing you to accept the proxy limitations in your overall system. In my case, I needed websockets. At the time, most stable proxies simply didn't support websockets. There was no way to tweak, add, or remove anything to fit my scenario. Game over.

## Movement to Modular
I expect to see more modularization of PaaS (for example, [these](http://stormpath.com/) guys in the area of user management) and that’s a good thing for early stage work at least. With all of this said, I currently default to a custom automated platform directly on IaaS. Typically on AWS, but increasingly on [Digital Ocean](https://www.digitalocean.com/) for cost reasons. Those selections are likely the topic of a future post.

## Stay Tuned
I have good intentions of open-sourcing some of my platform scripts if I can get time to make them usable. For now, here is a basic feature list:

* __Nginx reverse proxy__. Supports both static and dynamic content in a standardized way.
* __Full support for git deployments__. Utilizes commit hooks for all activities.
* __Assumed API and SPA architecture__. In other words, we’re defaulting to _apps_ instead of _sites_. This is definitely not about content.
* __Complete separation of front and back__. A natural way to manage the above architecture. Easily supports SPAs and mobile apps since a REST API is assumed.
* __Security and other basics__. I don’t go crazy here, but I install a firewall, swap space, upstart scripts, etc.


