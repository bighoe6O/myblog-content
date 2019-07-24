Title:  "Explorer: Menu Contextuel bash-here"
Date:   2018-09-21 06:41:36 +0200
Slug: system/explorer-menu-contextuel-bash-here
Tags: Windows


```
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\Directory\Background\shell\Bash Here]

[HKEY_CLASSES_ROOT\Directory\Background\shell\Bash Here\command]
@="C:\\tools\\msys64\\msys2_shell.cmd -where %V"
```
