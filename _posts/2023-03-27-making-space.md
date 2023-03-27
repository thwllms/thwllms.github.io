---
layout:     post
title:      "Making Space"
date:       2023-03-27 11:11:11
summary:    Reclaiming hard drive space with Docker Desktop and WSL2 on Windows 10.
categories: blog
---

My disk has been verging on 100% capacity for a long time. I've
always known that the problem is Docker, but I finally got around
to resolving it.

```
> docker system prune
```

This took a while to run, but cleared an embarassing amount of space.
I followed this up with optimizing Docker's `ext4.vhdx` file. 
The top answers on Stack Overflow point to an `Optimize-Vhd` command,
which wasn't found on my system. Instead, I followed
[these steps](https://github.com/microsoft/WSL/issues/4699#issuecomment-627133168).

Shut down Docker Desktop, then:
```
> wsl --shutdown
> diskpart
```

A new shell window opens with the Diskpart program running. Then from the Diskpart
command line:
```
> select vdisk file="C:\Users\…\ext4.vhdx"
> attach vdisk readonly
> compact vdisk
> detach vdisk
> exit
```
