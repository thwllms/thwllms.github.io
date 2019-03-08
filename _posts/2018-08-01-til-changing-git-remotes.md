---
layout:     post
title:      "TIL: switching git remotes"
date:       2018-08-01 12:00:00
summary:    Switching from GitLab to Bitbucket.
categories: blog
---

_Retroactively published on 8 Mar 2019. A while ago I started keeping a journal of TILs, and I've decided to share some of them._

At work we recently migrated our projects from GitLab to Bitbucket. (Sigh... I miss GitLab CI.) After the repositories
were copied to Bitbucket, I had reshuffle my git remotes and active branches to point to Bitbucket:

```
$ git remote rename origin upstream
$ git remote add origin <new-remote-ssh-url>
$ git checkout master
$ git branch --set-upstream-to origin/master
```
