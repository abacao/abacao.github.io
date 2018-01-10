---
layout: post
title: Meltdown and Spectre
---
As you might have heard, there are 2 new major vulnerabilities and they are called Meltdown and Spectre.

Both are tie to the CPU manufacturing and to a process of preparing in cache the next cpu instruction leading this to a vulnerability called "speculative execution"

But I'm here just to show some real effects in AWS Cloud.

Everyone that has any instance at AWS should update their machines.

At this moment, new RedHat instances are patched but new Ubuntu instances are not yet patched so they need to be patched ASAP after creation.

It’s not yet the final solution but it patches some stuff.


Please check the pictures provided.

RedHat out-of-the-box (only git was installed)
![](https://raw.githubusercontent.com/abacao/abacao.github.io/master/_post_pics/20180110-Redhat_aws.png)

Ubuntu 16.04 straight from AWS
![](https://raw.githubusercontent.com/abacao/abacao.github.io/master/_post_pics/20180110-Ubuntu_AWS.png)

Ubuntu 16.04 updated
![](https://raw.githubusercontent.com/abacao/abacao.github.io/master/_post_pics/20180110-Ubuntu_AWS_updated.png)

There are tons of reading to do if you want.
Some I found that where interesting are:
  [https://en.wikipedia.org/wiki/Meltdown_(security_vulnerability)](https://en.wikipedia.org/wiki/Meltdown_(security_vulnerability))
  [https://en.wikipedia.org/wiki/Spectre_(security_vulnerability)](https://en.wikipedia.org/wiki/Spectre_(security_vulnerability))

  Ubutu: [https://wiki.ubuntu.com/SecurityTeam/KnowledgeBase/SpectreAndMeltdown](https://wiki.ubuntu.com/SecurityTeam/KnowledgeBase/SpectreAndMeltdown) <br>
  RedHat: [https://access.redhat.com/security/cve/CVE-2017-5754](https://access.redhat.com/security/cve/CVE-2017-5754) <br>
  AWS: [https://alas.aws.amazon.com/ALAS-2018-939.html](https://alas.aws.amazon.com/ALAS-2018-939.html) <br>
  Nextcloud: [https://nextcloud.com/blog/security-flaw-in-intel-cpus-breaks-isolation-between-cloud-containers/](https://nextcloud.com/blog/security-flaw-in-intel-cpus-breaks-isolation-between-cloud-containers/) <br>

  Git repo used to show the status: [https://github.com/abacao/spectre-meltdown-checker](https://github.com/abacao/spectre-meltdown-checker)

AB
