---
layout: project
title: Grunt Connect Proxy
subtitle: Exercise Your API from Your Dev Server
categories:
- project
tags:
- grunt
- node
---

## Using Grunt with Grunt-Connect?
If you're using grunt for front-end development, you might also be using the [grunt-connect][gc] server to save some time. If so, you might have wondered how to proxy API requests without moving them to another domain in your client code. I recently ran across this problem and looked closer at grunt-connect for a possible solution. As it turns out, grunt-connect allows you to specify express-style "middleware" functions in the grunt configuration. For all the proxy heavy-lifting, I found the lightweight [connect-proxy][proxy] that was a perfect fit for this scenario.

[Here][gist] is the gist of how I did it.

### The Middlewares
It starts with a small middleware function to intercept HTTP calls to a particular endpoint (/api in this example). You could pass the endpoint via a config option, but I didn't need the flexibility. Anyway, grunt-connect allows you to add express-style middleware functions to the development server by simply adding them to a "middleware" array. Inside our single middleware function, we allow connect-proxy to proxy our /api request to a configured endpoint.

{% highlight javascript %}
// proxy-middleware from https://github.com/andrewrk/connect-proxy
var proxy = require('proxy-middleware')
  , url = require('url');

function middleware(connect, options, middlewares) {
  var proxyUrl = options.proxy || 'http://localhost:8000';
  var proxyOptions = url.parse(proxyUrl);
  proxyOptions.route = '/api';
  middlewares.push(proxy(proxyOptions));
  return middlewares;
}
{% endhighlight %}

### The Configuration
In the Gruntfile, just add a middleware and proxy option for various targets. The middleware option is looking for the above function. Each option can be selected by calling the appropriate grunt target.

{% highlight javascript %}
module.exports = function (grunt) {

  // Load grunt tasks automatically
  require('load-grunt-tasks')(grunt);

  // Time how long tasks take. Can help when optimizing build times
  require('time-grunt')(grunt);

  // Define the configuration for all the tasks
  grunt.initConfig({

    // Other grunt config stuff would go here

    // Here is the configuration for grunt-connect:
    connect: {
      options: {
        port: 9000,
        hostname: 'localhost',
        livereload: 35729,
        // Add the above proxy to the default connect configuration
        middleware: proxy,
        // Add the default API destination URL
        proxy: 'http://localhost:8000'
      },
      otherAPI: {
        // Add a different API destination URL
        proxy: 'http://localhost:8001'
      }
    }
  });

  // Register grunt tasks here

};
{% endhighlight %}


[gc]: https://github.com/gruntjs/grunt-contrib-connect
[proxy]: https://github.com/andrewrk/connect-proxy
[gist]: https://gist.github.com/spitimage/10084529