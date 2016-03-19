---
layout: post
title:  "Welcome to git!"
date:   2015-07-06 19:42:26
categories: git update
---

Basic commands
---
Cherry pick a single commit
>  git cherry-pick 5a4db2f512d8b72fbb36eca790f9d8e2215d63a1

Create gitignore file
> joe python jetbrains > .gitignore

Install git
> sudo apt-get install git-core bash-completion

Clone repo  
> git clone --branch master --depth 1 https://github.com/nginx/nginx.git

Download a single file from the bitbucket server  
> wget --user=msbanik --ask-password https://bitbucket.org/msbanik/bootstrap/raw/master/bash/aliases/centos.txt

Ammend last commit message  
> git commit --amend -m "New commit message"

Diff against a stash  
> git stash show -p stash@{0}

List stash
> git stash list

Apply top of stash and remove
> git stash pop

Undo last commit  
> git reset --soft HEAD~1
> git reset --hard HEAD~1

CRLF  
> git config core.autocrlf true

Revert changes made to your working copy  
> git checkout .

Revert changes made to the index (i.e., that you have added)  
> git reset

Revert a change that you have committed  
> git revert ...

List config
> git config -l

Remove unstage local changes
> git checkout path/to/file/to/revert 
> git checkout -- .

Listing branch
> git branch --list

Remove branch
> git branch -d branch_name

Create a branch develop, based on origin master
> git checkout origin/master -b develop

Set upstream or remote tracking for a branch
> git branch -u origin/master

Store windows password  
> http://gitcredentialstore.codeplex.com/