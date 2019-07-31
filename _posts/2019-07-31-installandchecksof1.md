---
layout: post
title: Check and install application
---

{{ page.title }}
================

<link href="css/blackboard.css" rel="stylesheet">


<pre><code>function Write-Host
  #variables
    $nameApp = "#env:appdata\app\app.exe"
    $LogFile = nameApp.log
  #codeApp
    if((Test-Path $nameApp) -match "True")
      {Logwrite "$nameApp exist" g
      . $nameApp
      }
    else{
      Logwrite "nameApp does not exist" r
      Start-Process - FilePath "path to the installed program"
      -ArgumentList "/S" -Wait -Passthru
      . $nameApp
        }
  Exiting n
</code></pre>
