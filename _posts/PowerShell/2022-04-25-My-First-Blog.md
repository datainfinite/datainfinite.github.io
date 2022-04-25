---
layout: post
title: "Restrict PowerShell Profile with conditional load"
subtitle: "Choose if you want to load the profile or not"
# date: 2022-04-25 06:07:13
background: "/img/posts/PowerShell.jpg"
categories: "PowerShell"
---

## This is testing for PowerShell

```powershell
[ValidateSet("Yes","No")]$x = Read-Host "Enter the one of the option you want to choose: YES/NO"
if ($x -eq "YES") {
    Write-Host "Powershell Profile loaded from $($profile)" -ForegroundColor Cyan -BackgroundColor Green
    $host.ui.RawUI.WindowTitle = "Windows PowerShell $hostversion is running with Profile loaded!! "
}
elseif ($x -eq "NO") {
    powershell.exe -NoProfile
    Write-Host "Powershell Profile not loaded from $($profile)" -ForegroundColor Red -BackgroundColor Green
    $host.ui.RawUI.WindowTitle = "Windows PowerShell $hostversion is running without Profile loaded!! "
}
else {
    powershell
}
```
