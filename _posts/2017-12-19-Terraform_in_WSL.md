---
layout: post
title: Terraform in WSL
---
Unfortunatly, in my work, I have to use Windows It started as Windows 7 and now I'm using a Windows 10 (not fully updated).

This is the way I found to install Terraform quickly in WSL (Ubuntu).

```
cd /tmp
wget https://releases.hashicorp.com/terraform/0.11.1/terraform_0.11.1_linux_amd64.zip
sudo mkdir -p /opt/terraform
sudo unzip /tmp/terraform_0.11.1_linux_amd64.zip -d /opt/terraform
export PATH="/opt/terraform:$PATH"
```

As I'm testing this, I will probably use my Terraform Snap package in a near future and maybe be able to run a full Linux system.

AB
