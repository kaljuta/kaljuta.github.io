---
layout: post
title: Swap window timer Windows
---

{{ page.title }}
================

<link href="css/blackboard.css" rel="stylesheet">

Create swap.vbs file:

<pre><code>function Write-Host
    set WshShell = WScript.CreateObject("WScript.WshShell")
    do while 1=1
    WScript.sleep 60000
    WScript.SendKeys "%{TAB}"
    loop
</code></pre>

Create powershell script:

<pre><code>Write-Host
     Start-Process "chrome.exe" "ip address" - WindowsStyle maximized
     Start-sleep - seconds 5
     Start-Process "path to the installed program"
     cscript swap.vbs
</code></pre>
