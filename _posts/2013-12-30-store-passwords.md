---
layout: post
title: Storing Passwords
categories:
- blog
tags:
- security
- passwords
---

## The Password Reality
There is no shortage of news and information to support the position that passwords are a terrible authentication mechanism. But even with solid alternative solutions, the password isn't going away any time soon. In the face of this reality, what are admins, ops folks, and developers to do?

## Consider Outsourcing
It is becoming more common for web and/or mobile applications to leverage some of the security mechanisms of the experts. This is especially true in the realm of authentication - everyone has seen something like this:

![][login]

This approach may raise other issues, but the security aspect is well spoken for. Naturally this approach still won't protect your users from their own bad practices, but that's true no matter what the solution is.

## The DIY Standard
If outsourcing is not an option, you might consider pondering the famous [quote][quote]:

> With great power there must also come - great responsibility!

Seriously. Passwords are often more than you think. If nothing else, consider that it's common for users to use the __same__ passwords for all their online accounts. Needless to say, a breach in _your_ site could be devastating. Here's the good news: _prevention is easy_.

I'm not a security expert, but I rely on _practical_ advice from experts and follow it closely. [This][article] article is a great place to start. Not a lot of folks like to delve into this stuff, so these guys are heroes in my book.

If you're in the password-storing business, please stay informed and continually evaluate your own practices.


[login]: /assets/images/SocialLogin.png
[quote]: http://en.wikiquote.org/wiki/Stan_Lee
[article]: https://crackstation.net/hashing-security.htm