# Favourite Papers Task Instructions
## Lab Git Workshop

Author: Flic Anderson

Date: 27 Nov 2020

**Git Workflow: Fork, Clone, Branch, Edit, Add, Commit, Push, Pull Request**

These instructions presume you've already got `git` set up (instructions[HERE](setup_git.md) if not), and you've already created a [GitHub](https://github.com/) user account.  If you haven't, please let me know and do those steps or none of the stuff below will work! :)

Here's the summary of what you'll need to do to add your favourite paper to the blog post on the lab website:

- [ ] fork the website in github (it copies all branches)
- [ ] clone (download) the fork to your local computer
- [ ] make branch (e.g."sams-favourite-paper")
- [ ] make edits to "blog/_posts/2020-11-26-favourite-papers.md"
- [ ] git add blog file
- [ ] git commit blog file with helpful message
- [ ] git push to your github (to remote)
- [ ] check on github the changes are there
- [ ] make pull request to Edward's repo (check it's "staging" branch)

As you can see, we're following the git workflow quite closely:

**Fork, Clone, Branch, Edit, Add, Commit, Push, Pull Request**

## On Github

As we've mentioned, GitHub is an online platform for storing git repositories. You can see the [Wallace Lab website](https://ewallace.github.io/) repository [HERE](https://github.com/ewallace/ewallace.github.io).  

*Open this in your browser and have a look at the page!*

Various tabs on the GitHub repository page show different options:

#### Code

Here you can see the 'code' (all the files and folders), details of when those files and folders were last changed, and various other details.  

It will also show you which `branch` of the repository you're viewing, in a drop-down menu towards the top left. The default view is the main branch, usually called the `master` branch. If you select other branches, you'll see the files from those branches. Keep an eye on which branch you're viewing, this is often where you can end up getting confused looking for files that don't exist in the branch you're viewing :)

A LICENCE file will tell you what you're allowed to do with the contents of the repo - if you can use any of the code or materials, and what you can do (ie if you can edit or change them, whether you have to attribute the original creators, whether you can use them in commercial or non-commercial ways etc.).

The README file is a key file which should contain information about the repository, and any details on how to get started using it.  It might include notes on how to contribute to it, or any citation information.

#### Issues

Here you'll see `issue tickets` which have been created to discuss or track issues, problems, new features or new ideas to be worked on in this repository. You can filter between 'closed' (completed or issues the repo owner has decided they won't fix), and 'open' issues (which might be in progress, or just 'to do').  You can add tags to specify types of issue.

#### Pull Requests

This tab will show any `pull requests` that have been made to the repository - where code from the repo has been edited (using `git add`, `git commit` and `git push` commands to track, describe and push the changes up to GitHub) and the code is waiting to be checked and reviewed by the repo owner.  The owner can then decide to accept and `merge` the changes into the repository, to add those changes.

We're going to make changes, create a pull request, and Edward will review them and merge them later to add them to the lab website repo!

### Forking The Repo

In order to make changes to the lab website, we want to be able to edit it. But we might not have access which allows us to directly edit Edward's repo.  We might also want to work in a 'copy' of the website to avoid breaking it with any changes.  

The best way to do this, is by working in a `fork` of the lab website.  This is effectively where we copy the git repository log which contains all the details of all the changes which make up all the files for the website.

We can then work in our personal `fork` (aka copy) of the original website, without fear of breaking anything on the website.  

#### Are you forked already?

You should be able to tell if you've already got a version of the lab website in a few ways.

You can try going to the lab website repository and attempting to fork it using the 'fork' button. If you already have a version forked, then it will tell you. Easy!  You can then click on it to view your fork. Great!

Alternatively you can check in your list of repositories, accessible from the top right corner of GitHub pages, where you can view your profile and settings etc. There's an option "Your Repositories" and you can scroll down to it, or filter "Type" by "fork" to see all your forks.

![](images/wallacelabwebsite_fork.png)

If you already have a fork of the lab website, there's an extra step to make sure you've got the latest changes in Edward's original repo!

Do you have a local (ie on your computer in front of you) folder called `ewallace.github.io`?  

## On Your Computer

If you DON'T have a folder called `ewallace.github.io`, you probably haven't `cloned` your fork of the repository yet. You can pass go and proceed to the next heading! (Do not collect £200).

If YES, you've already done the `git clone` step.  There are separate instructions to follow, because we want to make sure you've got those latest changes.  Please follow [THESE INSTRUCTIONS](already_forked.md) if you have a pre-existing fork of the lab website repo.

## From The Command Line

Here's the summary of what you'll need to do to add your favourite paper to the blog post on the lab website again (noting that we've already forked the website repository):

- [x] fork the website in github (it copies all branches)
- [ ] clone (download) the fork to your local computer
- [ ] make branch (e.g."sams-favourite-paper")
- [ ] make edits to "blog/_posts/2020-11-26-favourite-papers.md"
- [ ] git add blog file
- [ ] git commit blog file with helpful message
- [ ] git push to your github (to remote)
- [ ] check on github the changes are there
- [ ] make pull request to Edward's repo (check it's "staging" branch)

As a reminder, we'll be following the git workflow quite closely:

**Fork, Clone, Branch, Edit, Add, Commit, Push, Pull Request**

So let's go through it step by step.

## Git Clone

With the git command line terminal open in front of you, you want to run the following command:
`$ git clone https://github.com/FlicAnderson/ewallace.github.io.git` BUT REPLACE MY USERNAME WITH YOURS :)
NOTE: don't type the `$` in these instructions - this represents the command prompt (you'll see a corresponding `$` on your screen, showing that the terminal is expecting you to provide input). You might see this formatting in any documentation of code, and it means you need to type whatever comes afterwards as a command into the terminal.

This will clone (download) your fork (copy) of Edward's lab website repository.

You can then move into the `ewallace.github.io` folder from the terminal by using the `cd` (change directory) command.

You can use `git status` to check what branch you're on, what files have changed (and whether those changes have been recorded, or not), and it's super useful to do this regularly to keep yourself right.

Great!

- [x] clone (download) the fork to your local computer

## Make A Branch

Now we've got our copy of Edward's repo at our fingertips, we want to take another step to help keep our future changes organised.

You're probably in the default main `master` branch of the repository, but you can create other branches from that (which we'll do), move between different branches (which we'll also do!) and even create branches from other branches... (not today, Satan!)

So as Sam will talk more about branches later, I'll keep this brief, but... if you think about a repository as a universe, with all the files in it different planets and things, branches are like an ALTERNATE UNIVERSE, where the same planets have different details on them, like in this alternate universe I have a puppy instead of a kitten (MADNESS!).  

![](https://cdn.iwastesomuchtime.com/5f4543a4-f06a-4088-ad49-09cce2237e8f.jpg)

To get back to repos and branches, what this means is that you can keep different and totally separate sets of files in progress at once, without all of those changes carrying over between branches.

This is another way we can keep our favourite-papers task edits 'separate', to make them easier for Edward to view, review and approve.  

We can create a branch by choosing which existing branch we want to copy and start to work from.

Because we want to keep things simple, we're going to take the main `master` branch and make our alternate universe version from that.

We also need to think about how we name our branch.  There's a good convention which is quite handy if you're working collaboratively which is to name it after the feature or issue you're planning to fix/enhance/change. If you're working on something covered in an issue ticket (we'll talk about these more later if there's time), then you can include the number of that issue in the branch name.

Funnily enough, an issue ticket exists for THIS VERY TASK! [Check it out here](https://github.com/ewallace/ewallace.github.io/issues/53).

So, we might want to name our branch something like "favourite-papers-flic-53", so it's easy to see what it contains, find out more information in the issue ticket, and see who contributed it (optional, but useful for this task!).

When you make a branch, it copies the change log from **the branch you are currently in**, so always make sure you're in the right place or you'll end up confused later on.

You can check using:
`$  git branch`
This tells you which branches you've got locally, and an asterisk shows which one you're currently in.

If you aren't on `master` branch, you can change branches using `git checkout [branchname]` format, to move to the branch you name after `git checkout`. e.g. `$ git checkout master`.

Make the new branch using:
`$ git branch favourite-papers-flic-53`

Then (IMPORTANT!) change to that new branch using `git checkout favourite-papers-flic-53`.  If you forget and start editing in the wrong branch, it's fixable, but a hassle, so although you WILL forget in future (I do too), it's best to get into the habit of using `git status` to check where you're at frequently.

- [x] make branch (e.g."sams-favourite-paper-53")

## Edit The Blog Post

Now it's the part where you add your favourite paper info to the blog post!  

Once you know you're on the right branch, you can use your file browser and mouse and other such newfangled items to navigate to the `ewallace.github.io` folder and edit the file from a text editor if you like.  This isn't cheating, I do this ALL THE TIME, because working with text from the terminal is not easy on the eyes and can sometimes take longer than just pointing and clicking in notepad.

But you can also make your changes from the terminal using a text editor such as `nano` to open the file and add your text.  This is sometimes neccessary to do if you're working on a remote computer or server (for example trying to run things on Eddie computer cluster), where you might not have access to point and click options. But this is not THAT workshop, so do whatever you're comfortable with.

Open the blog post file, which you can find at:
`blog/_posts/2020-11-26-favourite-papers.md`

This means it's called "2020-11-26-favourite-papers.md", and inside a "_posts" folder, which is inside the "blog" folder.

It's a `.md` file, which means it's a markdown file. This is a great text file format which lets you do formatting without needing fancy menus or extra buttons etc.

Do your edits and save them!  

Markdown Tips:

* To add a hyperlink, you need to use the formatting: "[TEXT FOR LINK](LINK-URL)". You might link to the DOI of the paper for example.

* You can make things italic by enclosing them in 1 asterisk either side (e.g. "\*text\*").

* To make things bold, it's 2 asterisks either side (e.g. \*\*text\*\*)

* You can make a heading by using hashtags followed by a space before your text.
 \# Biggest heading
 \#\# Next size down heading
 \#\#\# Next size down heading
 \#\#\#\# etc...

You can find more information on markdown formatting [HERE](https://guides.github.com/features/mastering-markdown/).

- [x] make edits to "blog/_posts/2020-11-26-favourite-papers.md"

## Git Add

Now we've got our changes saved in whatever text editor we've used, we want to make sure `git` is tracking these changes, and is aware of all our good work.

We do this using `git add`.

We want to use `git status` to check what files have changed, and add the relevant ones to our repository change logs so they're recorded.

`$ git status`

This gives us input something like this:
```
fanders6@ceres:~/ewallace.github.io$ git status
On branch favourite-papers-flic-53
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   blog/_posts/2020-11-26-favourite-papers.md

no changes added to commit (use "git add" and/or "git commit -a")
```

It tells us which branch we're on, and a few hints on what we could type next.

We want to add the blog post file to git's change list, so first we need to `stage` it. We do that by running:

`$ git add blog/_posts/2020-11-26-favourite-papers.md`

If you run `git status` again, you'll now see that things have changed!

```
fanders6@ceres:~/ewallace.github.io$ git status
On branch favourite-papers-flic-53
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   blog/_posts/2020-11-26-favourite-papers.md

```
Git now 'knows' that our file has been modified, but it isn't yet officially 'recorded' in the change log.  This is because we might be making a lot of changes and git doesn't want to take up space by storing ALL of them.  It lets US choose when to take a 'snapshot' of our different files.

If you wanted to make another change to the file you still could, at this point.  You'd just want to make sure you ran `git add blog/_posts/2020-11-26-favourite-papers.md` again to re-add it.

If you wanted to UNDO your changes and go back to the original file, you can run `git reset HEAD blog/_posts/2020-11-26-favourite-papers.md` at this point.  This unstages and resets the file and basically goes back to the last 'recorded' set of changes git knows about.





- [ ] git add blog file
- [ ] git commit blog file with helpful message
- [ ] git push to your github (to remote)
- [ ] check on github the changes are there
- [ ] make pull request to Edward's repo (check it's "staging" branch)
