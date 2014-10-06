---
layout: post
title: "A Simple Git Config"
date: 2013-10-05 20:20:00
tags: note, git
---

Whenever setting up a new machine, I forget to properly configure Git. Usually
it is just the base things like name and email, but there are a few other useful
settings.

It is easy enough to run commands like `git config --global user.name "Mega
Man"` to setup Git options globally, but when setting up multiple options, it is
easiest to directly edit the settings in a file called `.gitconfig`. If you want
to start working with a `.gitconfig` file, run:

```
touch ~/.gitconfig
```

to create the file in your home directory. Go ahead and open it up in the editor
of choice. Below is what my `.gitconfig` looks like. I typically try to keep it
as simple as possible.

```
[user]
  name = Your Name
  email = youremail@host.com
[credential]
  helper = cache
[color]
  ui = true
[core]
  editor = vim
```

They credential setting for `helper = cache` defaults to a 15 minute remember
period for credentials. This is helpful for not having to continually type in a
password every time you need to push or pull.

The color setting for `ui = true` makes working with Git from the command line
just a little more colorful.

The core setting for `editor = vim` set the default editor for writing messages in Git. You can set this to whatever editor you want. I happen to use vim!

Beyond that, I keep my Git config lean and clean.
