# What To Do If You've Already Forked The Lab Website
## Setup Information for Lab Git Workshop

Author: Flic Anderson

Date: 26 Nov 2020


## On Github

You should be able to tell if you've already got a version of the lab website in a few ways.

You can try going to the lab website repository and attempting to fork it using the 'fork' button. If you already have a version forked, then it will tell you. Easy!  You can then click on it to view your fork. Great!

Alternatively you can check in your list of repositories, accessible from the top right corner of GitHub pages, where you can view your profile and settings etc. There's an option "Your Repositories" and you can scroll down to it, or filter "Type" by "fork" to see all your forks.

![]()


## On Commandline Git




## Flic's Example:

In case it's helpful, here's how the process looked for me. Bear in mind that some files may have changed, and you may see more/less/different branches depending on what changes have happened to the repo since!

This output shows me in the folder for my fork of the original repo:
```
# check status in the local copy of my fork of the repo; I was in a different branch (inclusivity-statement).
fanders6@ceres:~/ewallace.github.io$ git status
On branch inclusivity-statement
Your branch is up-to-date with 'origin/inclusivity-statement'.
nothing to commit, working tree clean

# check branches - here you can see the '*' shows which branch I'm currently in
fanders6@ceres:~/ewallace.github.io$ git branch
* inclusivity-statement
  master

# swap to master branch  
fanders6@ceres:~/ewallace.github.io$ git checkout master
Switched to branch 'master'
Your branch is up-to-date with 'origin/master'.

# check no changes in my github fork (was also hoping it'd pull changes from Edward's orig)
fanders6@ceres:~/ewallace.github.io$ git pull
Already up-to-date.
# nah... (I knew there'd been lots of changes lately to Edward's version, so I knew I didn't have them!)

# view existing remotes for this local copy of my github fork ('origin'); this shows 'my fork' as you can see from my username in the URL
fanders6@ceres:~/ewallace.github.io$ git remote --v
origin	https://github.com/FlicAnderson/ewallace.github.io.git (fetch)
origin	https://github.com/FlicAnderson/ewallace.github.io.git (push)

# add the original repo (as another remote, labelled 'upstream'; you can see Edward's username in the URL there
fanders6@ceres:~/ewallace.github.io$ git remote add upstream https://github.com/ewallace/ewallace.github.io.git
# get the lastest changes from original Edward website repo:
fanders6@ceres:~/ewallace.github.io$ git fetch upstream
remote: Enumerating objects: 25, done.
remote: Counting objects: 100% (25/25), done.
remote: Compressing objects: 100% (19/19), done.
remote: Total 25 (delta 9), reused 12 (delta 6), pack-reused 0
Unpacking objects: 100% (25/25), done.
From https://github.com/ewallace/ewallace.github.io
 * [new branch]      inclusivity-statement -> upstream/inclusivity-statement
 * [new branch]      lab-stuff-strains     -> upstream/lab-stuff-strains
 * [new branch]      master                -> upstream/master
 * [new branch]      protocols-io-23       -> upstream/protocols-io-23
 * [new branch]      staging               -> upstream/staging
# this is more like the changes I was expecting from the original repo! Yay.

# ensure I'm on master branch
fanders6@ceres:~/ewallace.github.io$ git checkout master
Already on 'master'
Your branch is up-to-date with 'origin/master'.

# Rebased: updated my local copy with the changes made in the original repo with my changes 'on top'
fanders6@ceres:~/ewallace.github.io$ git rebase upstream/master
First, rewinding head to replay your work on top of it...
Fast-forwarded master to upstream/master.

# pushed the updates (using -f to force them) from my updated local copy to my github remote version
fanders6@ceres:~/ewallace.github.io$ git push -f origin master
Username for 'https://github.com': FlicAnderson
Password for 'https://FlicAnderson@github.com':
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/FlicAnderson/ewallace.github.io.git
   14004f3..4869ce6  master -> master

# checked status
fanders6@ceres:~/ewallace.github.io$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean

# READY TO ROLL
```

Hope this helps!
