---
layout: post
title: Creating Software RAID 1 Mirrors in Debian
---

{{ page.title }}
================

<link href="css/blackboard.css" rel="stylesheet">

Check disk:
<pre><code>fdisk -l /dev/sdc /dev/sdd
</code></pre>

Example:
Check disk:
<pre><code>fdisk -l /dev/sdc /dev/sdd
</code></pre>


Create partitions like - fd - Linux raid. The discs that we are connected to RAID.
As a result, we get two disks and on each one partition for the entire disk:
<pre><code>/dev/sdc1        2048 3907029167 3907027120  1.8T fd Linux raid
/dev/sdd1        2048 3907029167 3907027120  1.8T fd Linux raid
</code></pre>


We assemble the RAID array itself:
<pre><code>mdadm --create --verbose /dev/md2 --level=1 --raid-devices=2 /dev/sdc1 /dev/sdd1
</code></pre>


After the system collects the array, the resynchronization process will begin.
We are waiting for the end of the resink:
<pre><code>cat /proc/mdstat
Personalities : [raid1] [linear] [multipath] [raid0] [raid6] [raid5] [raid4] [raid10]
md2 : active raid1 sdd1[1] sdc1[0]
      1953382464 blocks super 1.2 [2/2] [UU]
      [>....................]  resync =  1.3% (25956480/1953382464) finish=166.6min speed=192804K/sec
      bitmap: 15/15 pages [60KB], 65536KB chunk
</code></pre>


Create a file system on the array device:
<pre><code>mkfs.ext4 /dev/md2
</code></pre>


Raise the mirror after restart:
<pre><code>mdadm --examine --scan
ARRAY /dev/md/2  metadata=1.2 UUID=96fea4eb:5040d522:f83a5802:ea3b6a74 name=cs37907:2
</code></pre>
Edit /etc/mdadm/mdadm.conf and add the array above.


Update initframs:
<pre><code>update-initramfs -u
</code></pre>


Mount in / mnt:
<pre><code>mount /dev/md2 /mnt
</code></pre>


Add to fstab:
<pre><code>/dev/md2	/mnt	ext4	defaults	0	0
</code></pre>
