---
layout:     post
title:      "TIL: git checkout -m"
date:       2018-04-03 12:00:00
summary:    Undoing changes during a merge.
categories: blog
---

_Retroactively published on 8 Mar 2019. A while ago I started keeping a journal of TILs, and I've decided to share some of them._

You're doing a `git merge` and you hit some conflicts. You open an offending file and make changes. But then
you realize that you've made some *bad* changes. How do you get back to the original merged (albeit conflicted)
file?

```
$ git checkout -m <file>
```

Thanks to [this](https://gitster.livejournal.com/43665.html) post. 
