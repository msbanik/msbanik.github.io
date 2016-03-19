---
layout: post
title: Linux commands
---

List of some useful linux commands

Adding user
> adduser username 

Giving user sudo access
> visudo  
> sudo visudo

Add in the end
> username  ALL=(ALL)   NOPASSWD: ALL

Changing the default shell
> chsh -s /bin/zsh

List of shells
> cat /etc/shells

List recently modified files
> find . -type f -mmin -5
 
Adding build tools on Centos  
> sudo yum groupinstall 'Development Tools'

Adding build tools on Ubuntu  
> sudo apt-get install build-essentials

Viewing logfile
> less +F filename

Tail
> tail -n10; tail -f -n0 nginx_access.log | grep pattern

Get system limit information
> ulimit -a

Distribution version information
> lsb_release -a