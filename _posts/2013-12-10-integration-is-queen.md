---
layout: post
title: Integration Is Queen
categories:
- blog
tags:
- api
- integration
---

## The King and Queen
It has been said (at least once) that "[content is king][cik]". Then someone added that "distribution is queen". That may have been true, but I think the queen is getting a makeover and changing her name to _integration_. Yes, integration is queen. What do I mean by _integration_, and BTW what am I talking about? Hopefully I can eventually develop that here. This is the first post in a series on integration. We'll look at some history, architectures, and eventually lead to a focus on [Web APIs][webapi] and the related ecosystems.

## Brief History...
Before we start talking about APIs, it might be helpful to briefly consider the history of the web and the forces that got us to where we are today. As the internet came into existence, people used it like a road system. With the roads in place, the internet real estate soared - and the land grab was an inexpensive one. Sites were built at a mind-boggling rate. Before long, "sites" became the new store front. Not just a store front, but an entirely new distribution channel. So eventually sites became the central means to broadcast valuable content. And at that time, content was targeted directly at _people_. So the early days of the internet can be summed up in the interaction between 2 entities: __sites__ and __people__.

### Content Based Architecture
Not surprisingly, technology became focused on building sites and reaching people. Web servers and browsers. More web servers and more browsers. Browser wars. Wildfire open source [projects][apache] aimed at making web servers better (to make better sites). As technology became more optimized in this direction, the fidelity of the content suffered. Eventually, precious content became __blobs__ getting stuffed through the internet pipes. (I'm using the word __blob__ to describe content that is opaque - it requires a person to make sense of it). So Databases were mostly used for the sole purpose of quickly managing the blob. Web server technologies became optimized at quickly merging content into outgoing blobs. This architecture became known as "content management systems" (CMS). CMS solutions evolved to make it easier to author and otherwise create content - but always through the lens of presentation to _people_. The entire web became redefined by CMS. For example, [Wordpress][wp] (a _very_ popular CMS) has been called "[the web operating system][webos]". So what are the characteristics of this new web operating system? I'm calling it the _content based architecture_:

* Self-contained content with no real means of external integration (silos)
* Focused on isolated sites and keeping people engaged on the site
* Blob delivery
* Interoperable _only_ in terms of presentation (browsers -> people)

### Sites and Silos
Sites grew larger as content grew. And each site had impressive technology intensely focused on itself and its own content. Sure, the web supported the ability to link content, but there were conflicting motivations. How do you keep people on your site if you keep linking to someone else's site? Of course, the world did _not_ want silos - the world wanted a real "world wide web". Yet content providers were clearly not going to provide the solution. We all needed someone from the _outside_.

### The Outsider Silos
Try to imagine the web without the search engine. Impossible, right? Silos were a problem. Blobs were a problem. We were swimming in content, and there was no easy way to navigate the mess. Every site looked different and every blob looked different. Even as pipes were getting bigger and computers were getting faster, technology was no help. Until someone came up with the brilliant invention of robot web surfers. Yes, __many__ robots that (like people) surf the web _nonstop_, but take __great__ notes! Best of all, the robots could then have a compelling reason to send people to _their_ site to see their notes. So a new kind of content was born. Content about content. And a new kind of site was born, but it was still about _sites_ and _people_.

## And?
Obviously we're still here today. We cling to our search engines and search engine optimizations (SEO). Yet change is happening - it always does. For the next post, I'll share more thoughts on these exciting changes and possible implications for the future.


[webapi]: http://en.wikipedia.org/wiki/Web_API
[cik]: http://www.craigbailey.net/content-is-king-by-bill-gates/
[apache]: http://httpd.apache.org/
[wp]: http://wordpress.org/
[webos]: http://www.youtube.com/watch?feature=player_embedded&v=jkWiygLIkQI
