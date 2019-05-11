---
layout: post
title: Updating Git using Homebrew
date:   2015/08/28
comment: true
---

Whilst using Heroku to publish a new website, I got a warning that my Git version was out of date. Since I am using Homebrew to manage my versions, all i needed to do was updating within Homebrew:

`homebrew update git`

which duly updated it. However, running

`git --version` still produced the old version, git 2.0.1. 

Running `which git` produces usr/local/bin/git, which is Apples git, and we need to supercede with the Homebrew managed version. To fix this we need to:

* edit the .bash_profile (create one if necessary)
* add the line `export PATH="/usr/local/bin:$PATH"`
* restart your terminal app

`git --version` now produces 2.5.0, the latest version. It should also persist after system reboots. 


