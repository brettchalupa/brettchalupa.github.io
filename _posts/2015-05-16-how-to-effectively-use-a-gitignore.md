---
title: How To Effectively Use a .gitignore
date: 2015-05-20 5:00:00 -07:00
description: A guide to using .gitignore files.
tags:
- git
---

When working with a Git repository, you usually want to ignore files
that are not directly related to the codebase. This keeps the Git
repository clean and reduces clutter. For example, OS specific files
like the .DS_Store on OS X and Thumbs.db on Windows, databases,
directories like .vagrant/ that [Vagrant](https://www.vagrantup.com/)
creates, and temporary directories should be ignored. You can tell Git
to ignore files by creating a .gitignore file that contains the patterns
of files to ignore.

There are three common ways to use a .gitignore:

*   Project specific
* Directory specific
* Globally for the user

## Project Specific

This is what I think of when I think of a .gitignore. It lives at the
root directory of the Git repository, and it specifies what to ignore
for the project. For example, a Ruby on Rails project .gitignore with
explanatory comments may look like:

~~~
.bundle/               # ignore the Bundler cache
log/*.log              # ignore log files
config/application.yml # ignore application credentials
tmp/                   # ignore the temporary directory
~~~

The directories and files to ignore are specific to this project, since
it is a Ruby on Rails project. They are not files that should get
checked in, either because they are log files, a cache generated for
dependencies, contain secrets, or are not necessary.

Specific files can be ignored with `config/application.yml`, entire
directories can be ignored with `tmp/`, and patterns can be used to
match specific files like only files that end with .log in the log
directory with `log/*.log`.

## Directory Specific

A project can also contain directory specific .gitignore files. This is
less common, but it can be useful if a directory is used for a specific
purpose like provisioning a server or deploying.

For example, when using [Sunzi](https://github.com/kenn/sunzi) for
server provisioning, a .gitignore is created in the ‘sunzi’ directory in
the project that contains:

~~~
compiled/ # ignore the compiled deploy scripts
sunzi.yml # ignore the sunzi config that contains secrets
~~~

This makes sense to be in a directory specific .gitignore, because if
Sunzi is ever removed or replaced, the .gitignore for Sunzi-specific
files will get removed as well.

## Globally For the User

Have you ever seen a .gitignore for a project that is hundreds of lines
long that tries to ignore every possible file that could ever exist?
This is a bad practice because it muddies the history of the codebase
and bloats the .gitignore. If a developer starts using a different text
editor or IDE that creates temporary files or directories, the project
specific .gitignore should not care about user-specific files.

A simpler solution is to use a global .gitignore, which ignores the
specified files and directories for all Git repositories for the user.
When [setting up your Git config,](/a-simple-git-config)
the `excludesfile = ~/.gitignore_global` in the `[core]` settings allows
you to setup a .gitignore_global in your home directory that Git will
use for globally ignoring files. This is where IDE, OS, and tool
specific directories should be ignored.

This is not an extensive .gitignore_global, but it is enough to get
started:

~~~
.vagrant/ # ignore the dir Vagrant created
.DS_Store # ignore .DS_Store files on OS X
*.swp     # ignore swap files for vim
*.swo     # ignore swap files for vim</pre>
~~~

As you discover more files that should be globally ignored, continue to
add them to your `.gitignore_global`.

## Conclusion

Be diligent about not checking in any ole file into your codebase. The
codebase should, for the most part, just contain the code and any needed
assets.
