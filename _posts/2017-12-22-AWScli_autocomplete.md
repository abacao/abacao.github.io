---
layout: post
title: AWS Cli Autocomplete
---
If you are using WSL and AWS Cli, you might be missing the TAB to autocomplete.

Follow the instruction below and behold the magic.

```
which aws_completer
complete -C '/usr/local/bin/aws_completer' aws
```

If it works, you have to keep this instruction started in every bash, so:

```
vim ~/.bashrc
```
Add the next 2 lines to the bottom of the file.
```
which aws_completer
complete -C '/usr/local/bin/aws_completer' aws
```
Save, quit, start a new session and see if it worked.

AB
