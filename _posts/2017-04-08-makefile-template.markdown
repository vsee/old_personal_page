---
title: "C++ Makefile Template"
layout: post
date: 2017-04-08 08:25
image: /assets/images/markdown.jpg
headerImage: false
tag:
- C++
- Makefile
category: blog
author: vseeker
description: Makefile template for out of source C++ builds
---

I like using [gradle](https://gradle.org/) for Java projects because, if configured right, it takes care of the entire project layout upon build. Dependencies are downloaded and build directories are created in a nice standardised way. By using the [gradle wrapper](https://docs.gradle.org/current/userguide/gradle_wrapper.html), the build system does not even need to have gradle installed.

I was looking for something similar for C/C++ projects and found tools such as [CMake](https://cmake.org/) or [QMake](http://doc.qt.io/qt-4.8/qmake-manual.html) but none of them feels as straight forward as gradle. Admittedly, building native code does come with more system dependent hurdles than Java based projects. 

There is a [gradle package for native projects](https://docs.gradle.org/current/userguide/native_software.html) which seems to be worth a look (even though many C/C++ developers would probably cringe at the thought of using it). For now I settled for an [out of source Makefile template](https://gist.github.com/vsee/227ff0817856420da8636e1a2b8deb97) which seems to be a good start for native projects.

**UPDATE: 12.04.2017**
A drawback of the makefile template mentioned above is that it does not support out-of-source builds with multiple sublevel folders in the source directory. [This post](http://stackoverflow.com/a/39033569) provides one that does.

**UPDATE: 13.04.2017**
I adapted the [TimF's](http://stackoverflow.com/users/6413048/timf) makefile a bit and set up a [project template](https://github.com/vsee/makeTemplateOutOfSource) on github.
