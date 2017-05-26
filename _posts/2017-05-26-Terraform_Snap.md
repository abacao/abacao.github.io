---
layout: post
title: Terraform 0.9.6 and SNAPs
---

Another minor update on [Terraform](https://www.terraform.io/).

Some things to take a look:
  <br>[✓] New Provider: ovh
  <br>[✓] New Resource: aws_default_subnet
  <br>[✓] New Resource: aws_default_vpc
  <br>[✓] New Resource: aws_default_vpc_dhcp_options
  <br>[✓] New Data Source: aws_db_snapshot
  <br>...

With this release, I wanted to update my snapcrafts.
I have updated my packer snap and I have also created a terraform updated snap.

Both were build by the snapcraft.io servers that are linked to my github account.

```
computer:~$ snap find abacao
Name              Version  Developer  Notes  Summary
terraform-abacao  0.9.6    abacao     -      build, change, and version infrastructure safely and efficiently
packer-abacao     1.0.0    abacao     -      Packer - Build Automated Machine Images
```

You can find the changelog for Terraform  [here](https://github.com/hashicorp/terraform/blob/v0.9.6/CHANGELOG.md)

New Terraform 0.9.6 [here](https://www.terraform.io/downloads.html)

AB
