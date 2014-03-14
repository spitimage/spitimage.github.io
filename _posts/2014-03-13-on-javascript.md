---
layout: post
title: On Javascript
categories:
- blog
tags:
- javascript
- languages
---

## The Default Language
I recently met with an engineering team to discuss their options for software technologies and languages. Like many technology companies, they are discovering the power of software in general and the power of the cloud in particular to dramatically improve capability and market reach for their existing products. They are not a software company, so they are looking for ways to capitalize on these benefits without a dramatic change or expansion to their core competencies. They were looking for the 80% solution. In other words, what do I recommend as a default technology solution that will solve 80% of the problems (and likely more than that)? With each passing day, my answer increasingly converges on a single important technology. I start with Javascript.

## A Language Technology?
Sometimes a language is more than a language. Java is a great example of this. In some circles, the [JVM][jvm] is more relevant than Java the language. Virtual machines (VMs) are an elusive holy grail, and today we find ourselves with a new JVM: the _Javascript_ Virtual Machine. Yes, the implementation is entirely different, but I'm loosely calling it a VM in this post. Folks are actually talking about _javascript compilers_. Believe it or not, it sometimes makes sense to [compile][clang] C/C++ code into javascript using [emscripten][emscripten] for the purposes of leveraging this "VM". If that doesn't turn your paradigm upside down, I don't know what does.

## Not a Fanboy
To be perfectly honest, I am not a huge fan of the language. It is full of [warts][warts]. Without the help of an IDE, it is a structural nightmare. With almost no constraints, developers are actually encouraged to spew unreadable messes and generally abuse the language. And I personally just think it's ugly.

But then I remembered that the world isn't perfect. And for the following reasons, I jumped on the bandwagon.

### Way Under-Appreciated
Javascript is a superior language. Out of the box, it supports nearly all of the advanced features of any modern fashionable language:

* Support of any OO design pattern you can imagine
* Introspection and duck typing
* Functional
* Dynamic

Maybe [Douglas][douglas] says it best.

### Productivity
Once javascript is mastered, productivity soars. That's what [these][prod] folks say, anyway.

## Simply Ubiquitous
This VM is showing up everywhere. It has already thrived on virtually every PC/Mac/\*nix box for years now (browsers). Lately, the VM has found its way to other places too...

### Node.js
[Node][node] is a phenomenon. Even if you hate its guts, you can't ignore the noise. As I write this today, node is beginning the slide into the enterprise early adopters. See [here][adoption] and [here][adoption2]. These aren't ignorant technologists playing with a toy language.

#### Web Services
Need a lightweight REST API served by a technology that excels at IO-bound problems? How about:

* [Express][express]
* [Hapi][hapi]
* [Restify][restify]

Need a more traditional CMS that's easy on the resources? How about:

* [Ghost][ghost]
* [KeystoneJS][keystone]
* [Calipso][calipso]

#### Desktop Utilities(!)

* [Grunt][grunt]
* [Bower][bower]
* [Node Webkit][nwk]

### Mobile VM
Even mobile devices (smartphones and tablets, at least) have a full-featured VM installed. Today, it's still pretty hard for these devices to do anything substantial with javascript, but who needs to do anything substantial? Not me. Not often anyway. Believe me, that leaves a lot of realistic possibilities.

#### HTML5
Mobile browsers are starting to embrace more HTML5 features. Since javascript is the only language to realistically manipulate the DOM, an increase in HTML5 adoption will naturally drive javascript adoption and provide motivation for further performance improvements.

#### Hybrid Apps
Many mobile applications lend themselves well to the hybrid approach. With the hybrid approach, applications are written in javascript and layed out in HTML5. Hybrid technology has come a long way. Today it's possible to write an application once and deploy it on both iOS and Android.

## Performance Concerns
Google and others have invested significant resources in improving the [V8][v8] VM. Others are making similar investments on the mobile platforms. It's safe to say that the javascript VM is not getting slower. The same can be said about the hardware that runs it.

## Maximum Flexibility
With software written in a single language, you have the capability to deploy where it makes the most sense. Services can easily be moved within the cloud environment. Business logic and algorithms can run on either the server __or__ the client. This ability is nothing short of revolutionary.

## Simplified Coding
There are many benefits if an organization can successfully focus on a single language, including:

* No language "mental context switching" for developers
* A single set of coding standards
* Simpler testing and quality infrastructure
* A higher level of expertise due to smaller surface area

## Increasing Passionate Community
Needless to say, the javascript community is strong and healthy. A simple glance at local meetups, open source projects, the blogosphere, and even enterprise blogs give a good indication of the momentum. Like any open source technology, this critical mass leads to a higher quality product.

## It's Improving
Javascript is evolving and improving. The next release, [ECMAScript 6][ecma6], will eliminate some of the warts mentioned above while adding features that enable developers to leverage the strengths of the language more naturally.

[jvm]: http://en.wikipedia.org/wiki/Java_virtual_machine
[clang]: http://clang.llvm.org
[emscripten]: https://github.com/kripken/emscripten/wiki
[warts]: http://oreilly.com/javascript/excerpts/javascript-good-parts/bad-parts.html
[douglas]: http://javascript.crockford.com/javascript.html
[prod]: https://medium.com/the-javascript-collection
[node]: http://nodejs.org
[adoption]: http://blog.appfog.com/node-js-is-taking-over-the-enterprise-whether-you-like-it-or-not/
[adoption2]: https://github.com/joyent/node/wiki/Projects,-Applications,-and-Companies-Using-Node
[express]: http://expressjs.com
[hapi]: http://spumko.github.io
[restify]: http://mcavage.me/node-restify/
[ghost]: https://ghost.org
[keystone]: http://keystonejs.com
[calipso]: http://calip.so
[grunt]: http://gruntjs.com
[bower]: http://bower.io
[nwk]: https://github.com/rogerwang/node-webkit
[v8]: http://code.google.com/p/v8/
[ecma6]: http://www.ecmascript.org/docs.php
