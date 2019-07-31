Title: PowerShell
Date: 2019-07-24 09:20 +0200
Status: published
Slug: system/2019-07-24-powershell
Tags: Windows

# Ajoût de PowerShell au menu contextuel windows

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

# Profile

    Test-Path $profile
    False
    New-Item -path $profile -type file –force

[How to Change Windows PowerShell Color Scheme on Windows 10](https://beebom.com/how-change-powershell-color-scheme-windows-10/)

[Executing a command stored in a variable from PowerShell](https://stackoverflow.com/questions/3592851/executing-a-command-stored-in-a-variable-from-powershell)

    $cmd = '& 7z.exe a -tzip "c:\temp\with space\test2.zip" "C:\TEMP\with space\changelog"'
    Invoke-Expression $cmd

[How can I write a PowerShell alias with arguments in the middle?](https://stackoverflow.com/questions/4166370/how-can-i-write-a-powershell-alias-with-arguments-in-the-middle)
