---
layout: post
title: Quick start Zabbix Docker on debian 9.9.
---

{{ page.title }}
================

<link href="css/blackboard.css" rel="stylesheet">

Installing components for https and tools for working with a CA certificate

<code>apt install apt-transport-https ca-certificates dirmngr</code>

Adding GPG-key for repository

<code>apt-key adv - keyserver hkp: //p80.pool.sks-keyservers.net: 80 - recv-keys 58118E89F3A912897C070ADBF76221572C52609D</code>

Add repository file

<code>echo "deb https://apt.dockerproject.org/repo debian-stretch main" > /etc/apt/sources.list.d/docker.list</code>

<code>apt update</code>

<code>apt install docker-engine</code>
