---
layout: post
title:  "Post deployment on a fresh Linux VM"
date:   2017-04-18
categories: linux servers networking
---

Once again I find myself setting up a Linux VM and with that comes time to scour the internet for all the commands I forgot since last time.

How about I just some time and write a brief overview because hey, you might find it useful too?

# Creating a new user

If you're deploying a fresh Debian install, chances are it'll be `root` user by default. If you're on Ubuntu for example, you probably have a non-root account so this shouldn't be a problem.

Open up your handy dandy terminal and slap in the following command to create a new user

```bash
useradd -m -s [shell path eg; /bin/bash] username
```

We've got a few flags here:

`-m` creates your home directory as being `/home/username`. It's possible to have it live elsewhere but generally, I never have any reason to

`-s [shell]` lets us specify a custom shell. You'll be fine with `-s /bin/bash` by default but if you want to say, `-s /bin/zsh` to have `zsh` has your shell, make sure you have it installed before logging out. If it's not installed, you won't be able to log in as your new user until it's installed!

`username` is just whatever username you like and will be used for ssh too eg; `ssh username@ip`.

Once that's done, you 