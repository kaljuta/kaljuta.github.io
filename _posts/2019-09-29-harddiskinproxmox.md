---
layout: post
title: Forwarding a physical HDD to a virtual machine Proxmox
---

{{ page.title }}
================

<link href="css/blackboard.css" rel="stylesheet">

Example of forwarding a disk from a raid1 to a virtual machine.
Where set is the name of the virtual machine.
<pre><code>qm set 100 -virtio2 /dev/disk/by-id/scsi-36003005700ba2e00ff00002a02aec9e8
</code></pre>


Disk ID can be found in:
<pre><code>ls -l /dev/disk/by-id/
</code></pre>
