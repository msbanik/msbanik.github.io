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


Git config
---
Update config
> git config --global user.email "msbanik@gmail.com"  
> git config --global user.name "Madhusudan Banik"  

Windows
> C:/Users/mbanik/.gitconfig

Mac
> ~/.gitconfig

.gitconfig content
```
[user]
	name = mbanik
	email = madhusudan.banik@edenrockcomm.com
[alias]
	br = branch
	ck = checkout
	ci = commit
	st = stash
```


Git alias
---
```
git config --global alias.ci commit
git config --global alias.ck checkout
git config --global alias.br branch
git config --global alias.st stash
git config --global alias.up "git stash && git pull --rebase && git stash apply"
```

General idea
---
Git stash
> git pop == git apply + git drop

Git repo
---
https://github.com/torvalds/linux.git  
https://github.com/nginx/nginx.git  
https://github.com/rethinkdb/rethinkdb.git  
https://github.com/rogerwang/node-webkit.git  
https://github.com/ariya/phantomjs.git  
https://github.com/mysql/mysql-server.git  
https://github.com/mongodb/mongo.git  
https://github.com/antirez/redis.git  
https://github.com/python/cpython.git  
https://github.com/mackyle/sqlite.git  


Reference
---
https://www.atlassian.com/git/
http://durdn.com/blog/2012/11/22/must-have-git-aliases-advanced-examples/
http://haacked.com/archive/2014/07/28/github-flow-aliases/
https://codewords.recurse.com/issues/two/git-from-the-inside-out
http://stackoverflow.com/questions/161813/how-do-i-fix-merge-conflicts-in-git


git@bitbucket.org:msbanik/bootstrap.git
git archive --remote=git@bitbucket.org:msbanik/bootstrap.git HEAD:bash/aliases centos.txt|tar -x
git archive --remote=https://msbanik@bitbucket.org/msbanik/bootstrap.git HEAD:bash/aliases centos.txt|tar -x
curl https://msbanik@bitbucket.org/msbanik/bootstrap/bash/aliases/centos.txt

git diff --name-only --diff-filter=U


ls = log --pretty=format:"%C(yellow)%h%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate
ll = log --pretty=format:"%C(yellow)%h%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --numstat
lnc = log --pretty=format:"%h\\ %s\\ [%cn]"
lds = log --pretty=format:"%C(yellow)%h\\ %ad%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=short

git log --graph --oneline --all
git log --graph --pretty=oneline --abbrev-commit
gl=git log --oneline --all --graph --decorate  $*
ls=ls --color $*


core.symlinks=false
core.autocrlf=true
color.diff=auto
color.status=auto
color.branch=auto
color.interactive=true
pack.packsizelimit=2g
help.format=html
http.sslcainfo=/bin/curl-ca-bundle.crt
sendemail.smtpserver=/bin/msmtp.exe
diff.astextplain.textconv=astextplain
rebase.autosquash=true
alias.st=status
alias.ci=commit
alias.ck=checkout
alias.br=branch
core.autocrlf=false
color.ui=auto
user.name=Madhusudan Banik
user.email=madhusudan.banik@edenrockcomm.com
core.repositoryformatversion=0
core.filemode=false
core.bare=false
core.logallrefupdates=true
core.symlinks=false
core.ignorecase=true
core.hidedotfiles=dotGitOnly
gui.wmstate=normal
gui.geometry=1103x555+334+256 212 251


I want to create a remote branch and pull it locally

cd /path/to/my/repo
git remote add origin git@bitbucket.org:msbanik/remote_branch.git
git push -u origin --all # pushes up the repo and its refs for the first time
git push -u origin --tags # pushes up any tags
