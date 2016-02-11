---
layout: post
title: "Copying a tmux Buffer to the OS X Clipboard"
date: 2015-05-10 14:38:00
tags: note tmux terminal
---

I use tmux to manage and switch between multiple terminal sessions. tmux
is useful for editing files, watching a server log, and running tests
all in one window. A problem with using tmux is that if you
have vertically split panes, dragging the mouse cursor over text to
select it will highlight text in the neighbor vertical pane.

For example, if I try to select and copy the `git status` output, it
selects text from the `jekyll serve -w` pane:

![tmux multi-line text select example](/img/tmux-multi-line-text-select.png)

A way around this is to use the tmux flow of selecting text in a pane,
copying it tmux's buffer, and then moving that buffer into the OS X
clipboard.

~~~ sh
# enter buffer search/explore
Control+b [
# start selection
space
# copy selection to tmux buffer
enter
# transfer tmux buffer to OS X clipboard
tmux show-buffer | pbcopy
~~~

Now that output can be pasted anywhere by using Command+v.

_Note: This assumes that the key mode in tmux is set to vi._ -
`setw -g mode-keys vi`

P.S. To save a few keystrokes, I use an alias for the last step
called `tmcp`:

~~~ sh
alias tmcp="tmux show-buffer | pbcopy"
~~~
