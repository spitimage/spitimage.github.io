---
layout: project
title: Real Time HTML5 Plots
subtitle: Communications and Signal Processing
categories:
- project
tags:
- html5
- canvas
- websockets
- tornado
---

## Always Done it This Way
After spending years in this industry, I have seen the same problem come up on a repeated basis. Someone builds a great product (some sort of magic box or even magic system), then uses some sort of thick client UI framework for control and status. Usually the UI framework is not portable, much less standards-based. This happens even when the product owner goes through the trouble of providing clean and documented interfaces. This phenomenon may have something to do with a gap in skills between "traditional" software and "web" software.

_I wanted to bridge that gap._

## Standards-Based Approach
Many folks have been curious and skeptical of HTML5. Including me. So I worked with some of my clients to spec some control, status, and visualization capabilities based solely on the HTML5 and websocket standards. I integrated a web server proxy component to serve as a translation layer between their proprietary binary protocol and a JSON-based protocol. Besides protocol translation, the web server component provided data buffering and exposed a simple API to allow random access to the buffered data. The web server also served up the static assets and provided access control. On the client (browser) side, I wired [flot][flot] plots to the browser’s native websocket support. The UI provided the user with the capability to interact with the plots in various ways (such as mouse wheel and dragging). In the end, the product supported various zoom, pan, resizing, and marker capabilities.

## tl;dr
The solution works great with one caveat: websockets must be supported by the network. At the time we were testing this solution, we had issues with office firewalls and proxies. This is not a new issue with websockets _but_ the situation continues to get better with time. For most scenarios in this project, the user had a laptop plugged directly into the magic box and the network effects were not an issue.

### The Server
Python was my client's language of choice and I was plenty happy with that. I opted to use [tornado][tornado] for its great support of websockets. After creating the API layer and virtual devices, I implemented a device simulator to support client development. It was fun to solve the various rate and buffering problems inherent in our requirement to allow random data access by multiple clients.

### The Client
The rest is javascript. Since the API was pretty simple and message-based, I didn't need any websocket wrapper libraries. I just used the [standard][ws] client-side API. For all the plotting, [flot][flot] was an absolute joy to work with. It had the perfect amount of support for what I was trying to do. I found myself needing to gain access to the raw canvas, and flot never stood in the way.


#### Time Domain
In this plot, the time domain is on the X axis. This causes the plot to scroll to the left as it gets updated with the incoming signal.

![][td]

#### Frequency Domain
In this plot, the X axis displays frequencies. Like a [spectrum analyzer][sa], the signal changes are shown as amplitude changes over the whole frequency range.

![][fd]

### Screencast
Since we're talking about demonstrating _dynamic_ performance, this is a case where screenshots aren't enough. I put together a quick screencast [here][yt].

## Credits
[Ed][ed] did a great job taking this project over and filling in big gaps. Best contractor ever. I miss ya man!

[flot]: http://www.flotcharts.org/
[tornado]: http://www.tornadoweb.org/en/stable/
[ws]: http://www.w3.org/TR/websockets/
[yt]: http://www.youtube.com/watch?v=oPfhCQVkVqY
[td]: /assets/images/timedomain.png
[sa]: http://en.wikipedia.org/wiki/Spectrum_analyzer
[fd]: /assets/images/freqdomain.png
[ed]: https://github.com/eBurns
