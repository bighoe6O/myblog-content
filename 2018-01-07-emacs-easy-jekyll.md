---
layout: post
title:  "Emacs: easy-jekyll"
category: Jekyll
tags: [Emacs, Jekyll, Dev]
Date:   2018-01-07 14:43:31 +0100
---

# Installation du mode easy-jekyll

variable: easy-jekyll-base-dir: /home/stephane/repo/myblog

à positionner dans le répertoire: .dir-locals.el

	(setq easy-jekyll-basedir "~/repo/myblog")

<https://www.miskatonic.org/2014/01/26/more-about-emacs-and-jekyll/>

# Multiples blogs

```
 '(easy-jekyll-bloglist
   (quote
    (((easy-jekyll-basedir . "e:/repo/myblog")
      (easy-jekyll-url . "http://localhost/blog")
      (easy-jekyll-sshdomain . "duloup.org"))
     ((easy-jekyll-basedir . "e:/repo/Dev/arduino-doc")
      (easy-jekyll-url . "http://localhost/arduino-doc")
      (easy-jekyll-sshdomain . "duloup.org"))
     ((easy-jekyll-basedir . "e:/repo/Dev/scripts")
      (easy-jekyll-url . "http://localhost/scripts")
      (easy-jekyll-sshdomain . "duloup.org")))))
```
