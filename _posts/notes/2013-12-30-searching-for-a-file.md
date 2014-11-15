---
layout: post
title: "Searching for a File in the Terminal Using the find Command"
date: 2013-12-30 23:20:00
tags: note terminal
---

If you are looking for find a file based on its name, the `find` command does a
mighty good job at doing just that.

For example, if you are looking for an image with the name arrows in it, you
could use `find` in the following way:

```
$ find . -iname "arrows*"
./library/images/arrows.png
./library/images/arrowsAnimation.gif
```

The `-iname` flag is for a case-insensitive search. The `-name` command is used
for a case-sensitive search. The `*` is a wildcard; it looks for any file that
starts with arrows and is followed by anything else. It returns a list of the
file locations that match the search. The `.` directs the `find` command to
search in the current directory and its subdirectories.

If I wanted to find all PNG image files, I would use:

```
$ find . -iname "*.png"
./favicon.png
./_site/favicon.png
```

This looks for and outputs any file whose name ends in .png.

This is super useful for quickly finding where files are located. Enjoy!
