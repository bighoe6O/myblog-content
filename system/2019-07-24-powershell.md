Title: PowerShell
Date: 2019-07-24 09:20 +0200
Status: published
Slug: system/2019-07-24-powershell
Category: Système
Tags: Windows

<https://www.howtogeek.com/165268/how-to-add-open-powershell-here-to-the-context-menu-in-windows/>

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Classes\Directory\background\shell\powershellmenu]
@="Ouvrir PowerShell ici"

[HKEY_LOCAL_MACHINE\SOFTWARE\Classes\Directory\background\shell\powershellmenu\command]
@="C:\\Windows\\system32\\WindowsPowerShell\\v1.0\\powershell.exe -NoExit -Command Set-Location -LiteralPath '%v'"
```

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Classes\Directory\shell\powershellmenu]
@="Ouvrir PowerShell ici"

[HKEY_LOCAL_MACHINE\SOFTWARE\Classes\Directory\shell\powershellmenu\command]
@="C:\\Windows\\system32\\WindowsPowerShell\\v1.0\\powershell.exe -NoExit -Command Set-Location -LiteralPath '%L'"
```
