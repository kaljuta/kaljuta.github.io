---
layout: post
title: PC name, add PC domain, update windows 10 in powershell
---

{{ page.title }}
================

<link href="css/blackboard.css" rel="stylesheet">

Change PC name:

<pre><code>function Function{
    Write-Host
    Rename-Computer -ComputerName $ComputerName
</code></pre>


Add PC domain:

<pre><code>function Function{
    Write-Host
     add-computer -domainname test.corp; restart-computer
</code></pre>


Update windows 10:

<pre><code>Install-Module PSWindowsUpdate
Get-WindowsUpdate
Install-WindowsUpdate
</code></pre>
