---
layout: post
title: How to Solve an Expired Key (EXPKEYSIG) with Apt
---

{{ page.title }}
================

<link href="css/blackboard.css" rel="stylesheet">



<pre><code>sudo apt-key list
</code></pre>

You will see the expired key like this. Solution:

<pre><code>sudo apt-key adv --keyserver keys.gnupg.net --recv-keys 8C718D3B5072E1F5
</code></pre>
