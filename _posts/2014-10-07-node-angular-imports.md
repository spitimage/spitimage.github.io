---
layout: project
title: Importing Angular Services Into NodeJS
subtitle: An Unintrusive Approach
categories:
- project
tags:
- angularjs
- nodejs
- testing
---

## Isomorphicity
With all the talk about [isomorphic][isomorphic] javascript and all the popularity of [AngularJS][angular], you would expect to see more non-intrusive solutions along these lines. I'm not (yet) really looking for a way to _dynamically_ share code between client and server, but I often need to find a way to cleanly "import" client code into the Node environment to support API testing and a more unified unit testing approach.

## The Problem
Recently, I was working on an Angular project that included a REST API client. The API required a fair amount of payload manipulation, so I created Angular services to encapsulate all the marshalling/unmarshalling of JSON payloads. Aside from the Angular module declaration, all the code was pure javascript with no other dependencies. So how did I test this? I could have created mocks and spies with various [karma][karma] test cases, but this would have provided limited value. I really needed to know if my code worked with the real API - with real HTTP requests and a real API testing framework. The client-side framework is not designed for this. Isn't there a way to import pure JS Angular services and factories into a Node environment for this sort of thing?

## A Solution
Here are the [snippets][gist] with basic usage:

<script src="https://gist.github.com/spitimage/86fe983e9622ab2c3946.js"></script>

### What can be learned from this?

* How to import arbitrary JS code into a Node environment
* How to create Angular shims so Angular modules can be imported directly from the client project

### Limitations

* Injection is not supported, so this shim is only good for services and factories that have no Angular-specific dependencies.


[isomorphic]: http://isomorphic.net/
[angular]: https://angularjs.org/
[karma]: http://karma-runner.github.io/0.12/index.html
[gist]: https://gist.github.com/spitimage/86fe983e9622ab2c3946


