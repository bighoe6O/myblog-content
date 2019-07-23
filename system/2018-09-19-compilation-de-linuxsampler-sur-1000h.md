---
layout: post
title:  Compilation de Linuxsampler sur Asus 1000H
date:   2018-09-19 19:43:12 +0200
category: MAO
tags: [MAO, Linux]
---

<https://linuxsampler.org/debian.html>

<http://linuxsampler.org/downloads.html>

<https://raw.githubusercontent.com/pixelb/scripts/master/scripts/gcccpuopt>

	-march=atom -mfpmath=sse

https://wiki.gentoo.org/wiki/Asus_Eee_PC_1000H

	CHOST="i686-pc-linux-gnu"
	CFLAGS="-march=atom -O2 -fomit-frame-pointer -pipe -mfpmath=sse"
	CXXFLAGS="${CFLAGS}"
	
	CXXFLAGS="-march=atom -O2 -fomit-frame-pointer -pipe -mfpmath=sse" ./configure --prefix=/home/stephane/opt --mandir=\$${prefix}/share/man --infodir=\$${prefix}/share/info

