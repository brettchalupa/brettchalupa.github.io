---
layout: post
title: "Temporarily Ignore Changes for a File in Git"
date: 2013-09-19 23:20:00
tags: note, git
---

Sometimes you need to change a file in Git and maybe you don't want to
commit that change.

For example, let's say you adjust your `database.yml`
file in your Rails application to start with a fresh database and not
lose the one you are currently using. Those changes do not need to be committed to Git.
Instead of not just not adding that file with you stage your files to be
committed, you can temporarily ignore it by using the following command:

``` bash
git update-index --assume-unchanged file_name.rb
```

If you want to stop ignoring changes in the file, use the following
command:

``` bash
git update-index --no-assume-unchanged file_name.rb
```

This command can really make life simpler when you are changing a file
for local development where those changes do not need to be committed.
