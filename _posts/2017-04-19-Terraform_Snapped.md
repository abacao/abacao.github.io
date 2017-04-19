---
layout: post
title: Keeping Terraform Updated (using snap)
---

Fortunately or unfortunatly, I have several computers to manage and my main ones are macOS (work) and Linux (Ubuntu and Fedora).

In macOS I can use **brew update** to install and update but in Linux, there isn't a ways as easy as the mac... until now...

Introducing Terraform Snap package.

First of all, SNAPs are a new a exciting game changer. They are universal Linux packages (forget the war with deb and rpm).

To be able to run snaps you need to install snapd:

In Ubuntu:
```sudo apt install snapd```

In Fedora:
```sudo dnf install snapd```

Now you are able to install Terraform Snap package that will allow you to keep your Terraform updated automatically and magically.

For Terraform Snap

``sudo snap install terraform-snap``

The problem here (for now), is that the binary is now called "terraform-snap.tf"

To overcome this, I have created a alias like this:

``alias terraform='terraform-snap.tf'``

There is also a vault snap updated but the packer one is a bit out-of-date.

Have fun!
