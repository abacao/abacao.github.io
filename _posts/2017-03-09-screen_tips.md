---
layout: post
title: Screen util - Tips & why to use
---

Ever happened during some server installation, you really need to pack up and leave?
That happens to me almost every day and in the old days, I had to stop what I was doing and start all over again the next day.

Now I use **screen** as much as I can.

The exact definition of **screen** can be found here and it's like this:
```
Screen is a full-screen window manager that multiplexes a physical terminal
between several processes, typically interactive shells.
```

Basicly it's a always on shell within the shell.

First let's install it everyhere:

For Debian/Ubuntu:
```
apt install screen
```
For Fedora:
```
dnf install screen
```
For Centos/Redhat:
```
dnf install screen
```
For MacOSX:
```
brew install homebrew/dupes/screen
```

After it's installed, just run it: **$** ***screen***

First what you need to know it that **CTRL-a** is the command/super key.

For example:

After launching **screen**, run **top** in it. Now, what would you do to see a log file? Probably you would exit the top and see that log file or even star a new ssh login to your machine in order to do both actions at the same time but with **screen** you don't have to.

Press **CTRL-a c** and it will create a new window. Now run a **free -m**.

You can cycle the windows by pressing **CTRL-a n**.

It's like several virtual desktops in your terminal. Isn't that cool? But wait, the best is yet to come.

If you need to quickly logout but want the **top** command to keep on running, press **CRTL-a d** to detach from that screen.

You can even logout from your server and the **top** command will continue to run.

When you return to your server, run the command **screen -r** to re-attach to your screens that stayed running in the backgroud.

So in review:

| Command  | what it is doing |
|---|---|
| screen | it starts one session of scren util |
| screen -ls | list screen sessions |
| screen -r | re-attach to a screen session |
| screen -R | re-attach to a screen session if exists or start a new one |
| screen -t | re-attach to a screen session |
| screen -L | logging your screen session |
| screen -x | attach to a running screen (pair-programming) |
|
| CTRL-a c | creates a new window inside screen |
| CTRL-a n | cycle to next window inside screen |
| CTRL-a p | cycle to previous window inside screen |
| CTRL-a d | detach from screen |
| CTRL-a H | creates a running log of the session |
| CTRL-a x | lock your screen session (requires your key) |
| CTRL-a K | exit (or better, kill) the screen |

Njoy.
