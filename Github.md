---
up:
  - "[[100 A Floresta Aleatória]]"
stardate: Sep 24th 2023
update: Sep 24th 2023
---

```bash
# begin a new repository
git init

# clone your remote repository to have a local copy on different locations
git clone https://github.com/AnaCAvila/forest_regrowth.git
# note that the clone will create a new folder with the name YOUR-REPOSITORY
# can be done with https or ssh key

# to initiate a remote repository (origin) that already exists,
git remote add origin https://github.com/AnaCAvila/forest_regrowth.git

```

Apparently, there's issues using SSH, although it's a good option for people concerned about security. In general cases, stick with https.
==attention==: even with https you may need to authenticate on browser. If so, a pop up window will appear.


For obsidian, it's useful to have this in the config file:
```bash
[remote "origin"]
	url = https://[[personal access token]]@github.com/AnaZonia/moon_notes.git
	fetch = +refs/heads/*:refs/remotes/origin/*
```

### git bash
basically git's own terminal! easy to use on windows after you install git. good alternative to windows' trash CD language.

## git config

Git config is a way to set preferences of how to use hit, like git's "settings".

When you configure Git using the `git config` command, it writes these settings to the `.gitconfig` file.

It can have data such as your name, email, aliases for commands (ci = commit, for example)

```bash
# in case you need to add the email and name to config (after init and remote add origin)
git config --global user.email "aavila@mail.mcgill.ca"

git config --global user.name "AnaZonia"

git config --global user.password [insert personal access token]
```

The password is the personal access token. make sure it's open enough to allow proper handling of scripts.

Using GitHub CLI, the credentials are stored and initialized automatically. If needed, libsecret-devel must be installed (specially to use git with obsidian)

## git commit

```bash
# stage your changes
git add .
# adds all files, or also list only the ones you want to push

# if you want to undo git add 
git reset

# check staging area
git status

git commit -m "Your commit message here"
# m stands for message

# if you screw up the message and want to fix it,
git commit --amend

git push
```

## git branch

Creating a feature branch allows to make updates before making permanent pushes to the master branch.

![[Screenshot 2023-09-24 142014.png]]

```bash
# check out which branches do I have, and where you currently are
git branch

# create a new branch
git checkout -b feature-name-temp

# move to branch master
git checkout master

# delete a merged branch
git branch -d feature-name-temp
```

branches that are adding something new are usually called "feature branches"
## git pull / git merge

Pull requests help merge changes across branches or fork data from a remote repository.
It works in case you're working in a group - you branch the master, make your feature changes, then push your changes to the remote repository which opens a pull request for other members of the team to comment on.

Once the changes are accepted, we can do `git merge` or `git pull` to incorporate changes into the main branch

```bash
# to make sure your master branch is up to date
git pull origin master
# origin refers to the remote repository that was initially cloned

# make sure you're navigating to the branch you'd like to merge to master
git checkout feature-name-temp

# finally merge changes with the master branch
git merge master

# if there are conflicts, go resolve them and then continue the merge.
# git add is not necessary before merge, but you may need it if you alter files post-merge to solve conflicts
git add 'files that were changed'
git merge --continue

git commit -m 'message'

git push # origin master - check #origin section


```

![[Screenshot 2023-09-24 142630.png]]
## git rebase

Similar to merge, we can also use `git merge master`. Git rebase will reorder all commits made to the two branches that are being "rebased" in a way that it looks that all commits are being made to the same file.

It can be nice to feel like the project is more linear, and there's less registry of the splitting of the project into its branches. However, it "rewrites" commits so that they can work on top of each other out of chronological order, which can be bad if those commits have already been pushed to the remote repository and someone happens to be already working on the version of the commit that you have now altered and no longer exists!

![[Screenshot 2023-09-24 143749.png]]

Pros -> more linear, clearer history. Looks like all the changes were made straight on master! ==great to keep local commits looking clean within feature branches!==

Cons -> no idea when changes were made in parallel, everything looks like it was made in a sequence, so it's hard to tell each contribution apart. ==terrible to use on commits that someone else is working with!== 

I think rebase could work well for feature branches, when I am working alone and don't really want a detailed history of all the separate "trips" I took away from the master branch, only want a clear registry of when which change was made.


## git fetch

Gets all information from the remote repository without merging it to local branches. Different from git pull, which merges the remote with the local.

The information fetched is not stored in the local folders, but kept in "remote tracking branches" called 'origin/master', 'origin/feature1', so on and so forth.

it's useful when you want to first check out the changes that were made and edit them before merging into your local repo.

```bash
# After fetching origin/master and making all changes, merge the changes into your local branch (e.g., "master") 
git merge origin/master
```

## git log / git diff

These commands are used to look at history of alterations done to a file or branch, or compare the histories of branches, files and commits.

The .. operator helps look at the ranges between commits (constrains it to the range you want)

```bash
# see your whole commit history
git log

# View the changes that were fetched
git log origin/master
# gives a history of alterations and commits done to the origin/master branch

# to see the differences between your current branch and origin/master,
git diff origin/master
# compares it with your local repo

# compare changes between two commits
git diff <commit1> <commit2>

# see all the history of commits that happened since splitting of the branches
git diff branch1..branch2
```

## origin

Origin means the default remote repository that you are linked to (the one you created or cloned). 
```bash
# lists all remote repositories associated with your local repository
git remote -v

# to be very specific to which remote repository you want to push to
git push origin master
```

## .gitignore

[.gitignore](https://www.freecodecamp.org/news/gitignore-file-how-to-ignore-files-and-folders-in-git/) is a file that lists the folders or files that you do not want to add to the repository.
- the file starting with . is not visible with ls command. to view hidden files, we must use "ls -a" or "la"

```bash
# create .gitignore
touch .gitignore

# ignore a directory
directory/

# Ignore directories with "data" in their name
**/*data*/

# matches any files and directories with the name test
test

# ignore text in root repository
/text.txt

# ignores all .md files
*.md

# does not ignore the README.md file
!README.md

# ignore all with a name starting in img
img*

# add .env file to .gitignore
echo ".env" >> .gitignore
# remove env file from git index
git rm --cached .env

```
The `git rm` command, along with the `--cached` option, deletes the file from the repository but does not delete the actual file. This means the file remains on your local system and in your working directory as an ignored file.

Right now, I have my gitignore file ignoring folders with large data or virtual environment directories.

[One example of a gitignore file for a project using R and Python](https://www.toptal.com/developers/gitignore/api/python,r)
## Resources

[GitHub Skills](https://skills.github.com/)