---
layout: post
title:  explorer-menu-contextuel-bash-here
date:   2018-09-21 06:41:36 +0200
category: Système
tags: [Système, Windows]
---

```
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\Directory\Background\shell\Bash Here]

[HKEY_CLASSES_ROOT\Directory\Background\shell\Bash Here\command]
@="C:\\tools\\msys64\\msys2_shell.cmd -where %V"
```
