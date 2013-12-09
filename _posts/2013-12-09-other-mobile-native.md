---
layout: post
title: Unsung Cross-Platform Hero
categories:
- blog
tags:
- mobile
- c
- c++
---

## HTML5? Guess Again!
In most developer circles, talk of cross-platform development immediately leads to a discussion about the merits of HTML5. More specifically, javascript as the new mobile VM. As you might suspect, the world is much bigger than this. I thought I would briefly highlight another approach that is anything but trendy. Yet it can be the _perfect_ solution in many scenarios...

## One Language...
What if I told you it was possible to write most of your app __once__ _and_ __not__ in javascript? What if I also told you that the secret lies in writing _native_ code?

## Native Code?
It's a common belief that native code in Android is written in java while native code in iOS is written in Objectiv-C. Not so fast. A stricter definition for "native" code is really talking about the actual instructions being executed by the processor. So far, there isn't a ubiquitous processor that understands Java. The same is true for Objective-C (although it is much closer since it's technically compiled into native instructions). The key is finding a language that is high-level enough to be productive yet can run natively in both environments. What's the greatest common denominator?

## No Surprises
As it turns out, Objective-C is a superset of C. It may be a little-known fact, but you can actually run C code in your iOS app without any special effort. That doesn't help us _unless_ we could get that same C code to run on an Android device. These devices generally run with the same processors, so that isn't a problem. Really it's a question of how difficult it is to develop C code for Android. As it turns out, this [support][ndk] has been with Android from the very beginning. Now if you look closely at that link, you might notice that C++ is also supported (they're just using the GNU compilers). Since Apple is technically using the [Clang][clang] compiler, iOS apps can also take advantage of C++. So it really looks like C++ __can__ serve as the language for cross-platform development! What's the catch?

## Drawbacks
### Compilation
By definition, native code must be compiled for every platform it runs on. So for a cross-platform situation, you would need to compile your native code for every device. Bummer.

### High But Low
C++ is a great language for many things, but it is not really the best language for business logic. There needs to be a very compelling reason to leverage C++. In other words, cross-platform certainly is not enough. Here are some areas where C++ may be a good solution:

* CPU-intensive algorithms and calculations
* Anything pushing the limits of device I/O throughput
* Anything that may require custom memory management
* Anything using lots of device memory
* Anything that does 3D graphics
* You get the idea

### Libraries
Anything substantial written in C++ will certainly use libraries. And those libraries will almost certainly use other libraries. It is essential to do plenty of homework on each library in use. Is the library mobile-friendly? Will this library be compatible on the other X platforms?

## In the Real World
### Dropbox
[Here][dropbox] is a video of some DropBox engineers giving an overview of their native cross-platform approach.

### OpenGL Situations
[Here][openglproj] is a link to a project that shows how to write native cross-platform code using [OpenGL][opengl].

## Conclusion
Even if C++ won't be the first tool you choose for your cross-platform needs, it should have a special place in your toolbox. It's easy to forget that the __vast__ majority of all software is 1) written in C/C++ or 2) runs on a VM that is written in C/C++. Sounds like a powerful tool to have!


[ndk]: http://developer.android.com/tools/sdk/ndk/index.html
[clang]: http://clang.llvm.org/
[dropbox]: http://www.youtube.com/watch?v=S5rXCvu9-NM
[openglproj]: http://www.learnopengles.com/developing-a-simple-game-of-air-hockey-using-c-and-opengl-es-2-for-android-ios-and-the-web/
[opengl]: http://www.opengl.org/
