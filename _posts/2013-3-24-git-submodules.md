---
layout: post
title: magical dependency management with git submodules
category: GIT
published: true
---

Managing dependecies can be a total pain.
If your language has a well-supported package manager like npm, pypi, or bundler, then this isn't a huge issue.
However, if you're working in a language without such features, or are using an unpopular project, it gets ugly very quickly.

A common strategy is to copy the project's contents into your own project.
This method is the simplest to deploy, but it makes upgrades very difficult.
It also messes with the stats of your project, and, most importantly, your pretty Github graphs.

Another strategy is to make the user download each dependency and incorporate it into the project.
As everyone knows, users love bumbling around the internet searching for the correct version of a package.
They love it almost as much as they love copy-pasting terminal commands from the internet.

Some projects require a lengthy setup process where the user downloads each dependency when they download your project.
This makes the project much harder for the user, and much easier to mess up.

To solve these problems, I present:

# git submodules

Git submodules allow you to essentially symlink to another git project.
The code is there as if it were on your system locally, but it's not.

Let's go through an example. Say you want to add [FontAwesome](http://fortawesome.github.com/Font-Awesome/) to your website.

```bash
$ git submodule add git://github.com/FortAwesome/Font-Awesome.git submodules/fontawesome
```

Bam. Now check out 


```bash
$ git submodule -h
Usage: git submodule [--quiet] add [-b <branch>] [-f|--force] [--name <name>] [--reference <repository>] [--] <repository> [<path>]
   or: git submodule [--quiet] status [--cached] [--recursive] [--] [<path>...]
   or: git submodule [--quiet] init [--] [<path>...]
   or: git submodule [--quiet] update [--init] [--remote] [-N|--no-fetch] [-f|--force] [--rebase] [--reference <repository>] [--merge] [--recursive] [--] [<path>...]
   or: git submodule [--quiet] summary [--cached|--files] [--summary-limit <n>] [commit] [--] [<path>...]
   or: git submodule [--quiet] foreach [--recursive] <command>
   or: git submodule [--quiet] sync [--recursive] [--] [<path>...]
```

## Learn More

The [reference page for git submodules](http://git-scm.com/book/en/Git-Tools-Submodules)
