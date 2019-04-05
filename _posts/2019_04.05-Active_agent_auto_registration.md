---
layout: post
title: Active agent auto-registration host Windows
---

{{ page.title }}
================

<link href="css/blackboard.css" rel="stylesheet">

1. Config agent zabbix, on Windows hosts:

<pre><code>^LogFile=c:\zabbix_agentd.log
Server=IP_zabbix_server
ServerActive=IP_zabbix_server
HostnameItem=system.hostname
HostMetadata=windows
</code></pre>

2. Create an action in the frontend zabbix:
Configuration -> Actions, select Auto registration as the event source and click on Create action:

In the Action tab, give your action a name
Optionally specify conditions. If you are going to use the “Host metadata” condition, see the next section.
In the Operations tab, add relevant operations, such as - 'Add host',
'Add to host groups' (for example, Discovered hosts), 'Link to templates', etc.
