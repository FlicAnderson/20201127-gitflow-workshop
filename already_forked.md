# What To Do If You've Already Forked The Lab Website
## Setup Information for Lab Git Workshop

Author: Flic Anderson

Date: 26 Nov 2020


## On Github

You should be able to tell if you've already got a version of the lab website in a few ways.

You can try going to the lab website repository and attempting to fork it using the 'fork' button. If you already have a version forked, then it will tell you. Easy!  You can then click on it to view your fork. Great!

Alternatively you can check in your list of repositories, accessible from the top right corner of GitHub pages, where you can view your profile and settings etc. There's an option "Your Repositories" and you can scroll down to it, or filter "Type" by "fork" to see all your forks.

![]()

If you already have a fork of the lab website, there's an extra step to make sure you've got the latest changes in Edward's original repo!

Do you have a local folder called `ewallace.github.io`?  

## On Commandline Git

If you DON'T have a folder called `ewallace.github.io`, you probably haven't `cloned` your fork of the repository yet. From your home folder, or wherever you want the repository to go:
`git clone https://github.com/FlicAnderson/ewallace.github.io.git`
BUT, remember to replace the URL with the one you've copied from the page of your fork of the lab website on your GitHub page. 

If YES, you've already done the `git clone` step.  You want to move into that folder from the git terminal (command line). You can do that using the `cd` command:
`$ cd ewallace.github.io`
NOTE: don't type the `$` - this is commonly used when showing code to represent the command 'prompt' and let you know to type what comes afterwards.

Swap to the `master` branch using the command `git checkout` followed by the name of the branch you want to switch to. You can usually use tab to autocomplete after typing the first few letters.
`$ git checkout master`

Check whether you have a `remote` set up for this branch. You can do this using the command:
`$ git remote --v`
The `--v` stands for 'view'. You might expect to see the URL for your fork there.

Next we want to add the original repo as another remote (ie we want to connect our local repo to the 'remote' one on GitHub to be able to see all the recent new changes).
We can do this using the following command (and we're nicknaming the original lab website repo as "upstream"):
`$ git remote add upstream https://github.com/ewallace/ewallace.github.io.git`

We then want to `fetch` the latest changes from the original lab website repo to make sure we're up to date and can access the blog post. We can use `git fetch` followed by the name of the 'remote' location we want to get them from.
`$ git fetch upstream`
NOTE: this is similar to using `git pull` to get changes, but it doesn't automatically `git merge` any of the changes. `git fetch` just checks to see if there are any changes without doing anything about them.

This means we need to follow it up with another command (after checking we're definitely on the `master` branch) to add those recent changes from the original into any changes we've got in our local repository:
```
# ensure we're on master branch
$ git checkout master

# apply the changes from the original repo (upstream) to our local ones
$ git rebase upstream/master
```
Using `git rebase` will update my local copy with the changes made in the original repo with my changes 'on top'.  There are a few different commands to combine different sets of changes, and you will maybe never use `git rebase` again - I think this may have been the first time I've ever used it!

Last but not least, we want to make sure that these combined changes (any of our local ones and any recent ones from Edward's original repo) get added to our GitHub copy, so we can see them there too!

We do that by using `git push`, with a few extra arguments to the command to 'force' (`-f`) these newly combined changes up the pipe to GitHub. Here, `origin` is the name of our GitHub fork of the lab we saw listed as one of our 'remotes' earlier when we ran `git remote --v` to view them. `master` is the name of our branch.
`$ git push -f origin master`

The final thing we can do is to use `git status` to check everything is good, and we're ready to move on and get branching and editing.

Remember that this is the pattern we roughly want to follow:

**Fork, Clone, Branch, Edit, Add, Commit, Push, Pull Request**


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
