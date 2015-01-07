---
layout: post
title: Authentication Hacks
categories:
- blog
tags:
- security
- passwords
- identity
---

# What is Going On?
It seems like everyone is getting hacked or breached these days. I guess we shouldn't be surprised since security experts have been warning about this for years. It's interesting to see how quickly the issue has forced itself into the spotlight. From international _cyber wars_ to high profile _basement hackers_, it seems to be everywhere.

I'm no security expert, but I'm personally affected at many levels. As a web application developer, I feel obligated to stay on top of this issue. Maybe even ahead of it. Nobody can guarantee 100% security, but it's __very__ helpful to look where most of the failures are happening today - then focus on those first.

# Glaring Attack Vector
Breaches mostly occur because of a failure to properly _identify_ an intruder as such. In other words, intruders most often gain access by masquerading as someone else. This is a failure in _authentication_. Authentication is the process of properly verifying that a person is who they claim to be. So, I'm simply saying that __if__ we were better at authentication, the number of breaches would be __drastically__ reduced. As you probably guessed, this is easier said than done.

# Path of Least Resistance
There are many good ways to provide authentication. They are all inconvenient. There are many bad ways to provide authentication. They are (mostly) all convenient. Funny how that works. The real world __so__ needs a happy medium! So as everyone is painfully aware, we have _most certainly_ settled on a de facto standard. Yes the beloved _username_ and _password_. Volumes have been written on this topic by people far more passionate than [I][eyeris]. To boil it all down for this measly post, I'd simply say that times have changed. Today's technology eats passwords for breakfast while culture makes the job easier. 

# Lean On Who? 
With all the troubles that passwords can cause, what are we to do? Well, we can take comfort in the fact that the _real_ experts aren't surprised by our current situation. They have proposed some valid alternatives, but this sort of change can take __lots__ of time. In the short term, we've seen the rise of "two factor authentication" ([2FA][2fa]) solutions. Based on what the experts are saying, 2FA makes a __huge__ difference from a security perspective. Many of these experts have made it happen in some familiar places:

* [Google][google2fa]
* [Facebook][fb2fa]
* [Github][gh2fa]
* [Twitter][twitter2fa]
* Many More!

Is there a way for the rest of us to benefit from the fruits of their labor? In a word, __yes__! All of the above-mentioned companies actually provide a way for me (lowly web application developer) to effectively outsource the job of authentication to them. Technically, this is pretty straightforward and well-documented in their respective documentation. So that helps eliminate one problem. But it creates another!

# To Each His Own
We're in the early days of this idea of "outsourced authentication", so we don't really have good open standards to rely on. As you can imagine, each of the above providers solves the problem a bit differently. As a web application developer, I would like some way to decouple my application from all the provider nuances. To this end, I have been working on such a [project][jwtc]. 

_To be continued..._


[eyeris]: https://github.com/spitimage/eyeris/wiki
[2fa]: http://en.wikipedia.org/wiki/Two_factor_authentication
[google2fa]: https://www.google.com/landing/2step/
[fb2fa]: https://www.authy.com/add-2-factor-authentication-facebook
[gh2fa]: https://help.github.com/articles/about-two-factor-authentication/
[twitter2fa]: https://blog.twitter.com/2013/getting-started-with-login-verification
[jwtc]: https://github.com/spitimage/jwt-central
