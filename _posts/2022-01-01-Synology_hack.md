---
layout: post
title: Synology hack
---

Goal: having a new NAS with more capacity (CPU, RAM and storage).

Steps:
* Spend money on a new NAS (Synology 920+)
* Spend money on 3.5" drives (4x4TB WD Red)
* Spend money on DDR4 stick of ram (16Gb)
* Spend money on a NVME drive for essentials (512Gb 970Pro)

Synology only officially supports 8Gb of RAM on this system but there were stories about the extra RAM possible am I give it a try. So now I have a NAS with 20Gb of RAM.

Synology also does not allow the SSDs NVMEs to function as storage, only as CACHE which was not needed for my workload and I seamed as a challenge.


## Steps to reproduce:

Login via SSH and excalate to root:

```
ls /dev/nvme*
```
```
fdisk -l /dev/nvme0n1
```
```
synopartition --part /dev/nvme0n1 12
```
```
cat /proc/mdstat
```
```
mdadm --create /dev/md3 --level=1 --raid-devices=1 --force /dev/nvme0n1p3
```
```
mkfs.ext4 -F /dev/md3
```
```
reboot
```

After that, nothing really happens until you go on the 3 dotted menu and select "Online Assemble" and voilá, new SSD Volume for fun with docker and machines.

Be aware that Synology does not support this due to the lack of cooling, so keep an eye on temps!

This was done with **Synology 7.0.1-42218**

AB
