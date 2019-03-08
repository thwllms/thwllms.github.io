---
layout:     post
title:      "TIL: the sticky bit"
date:       2018-10-07 12:00:00
summary:    Permissions on a shared folder.
categories: blog
---

_Retroactively published on 8 Mar 2019. A while ago I started keeping a journal of TILs, and I've decided to share some of them._

Today I learned about the [sticky bit](https://en.wikipedia.org/wiki/Sticky_bit).

I set up a Samba share on a Raspberry Pi for our household scanner. The scanner dumps files into this folder,
and we can triage them from our computers or phones. It seemed to be working fine, but then I realized
that I wasn't able to delete files. I could create and read files, but delete just didn't work.

Here's how the directory looked:

```
$ ls -lah / | grep scanner
drwxrwxrwt   2 scanner scanner 4.0K Oct  7 18:52 scanner
```

At first I figured there was some sort of group permissions problem. But adding my user to the `scanner` group
didn't solve it.

Turns out it was the `t` - the [sticky bit](https://en.wikipedia.org/wiki/Sticky_bit). This was preventing any user who wasn't `scanner` from deleting
files in that directory.

Removing the sticky bit fixed the problem.

```
$ sudo chmod -t /scanner
```

