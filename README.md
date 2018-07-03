<!-- $theme: gaia -->

Git
===
By Thibaut Vincent

---

# What is Git
- Verison Control System
	- Keep track of files
	- Keep history of every file
- Distributed
	- Works offline & online

---


# Installation & basic configuration

- Download the Git binary from git-scm.com (Windows)
- Set default credentials
```
$ git config --global user.name "Lorem Ipsum"
$ git config --global user.email lorem@ips.um
```

---

# GIT GUI's (not recommanded)
- Some very basic GUIS
- Other Git GUIs also exist
	- Windows: Sourcetree, TortoiseGit, SmartGit, etc.
	- OS X: Sourcetree, Tower (paid), etc.

---

# Getting started

---

# Creating repository
- Start tracking files in a directory with
`git init`

- Autocreation of `.git` folder
	- Meta information
	- History
	- Hooks (pre-commit checking, etc)
	- ...

---

# Initializing of my project (example)
```sh
thibaut in ~/Projects/git-class-osoc
$ git init
Initialized empty Git repository in /Users/thibautvincent/Projects/git-demo/.git/
```

---

# Working on existing files in repository
- Start working on files
 `git clone git@github.com:thibautvincent/git-class-osoc.git`

---

# After changing files

## Check the status
`git status`
```sh
thibaut in ~/Projects/git-class-osoc
$ git status
#
# Untracked files:
#	index.html
#
```
Git compares the current state to the last state stored in the history

---


# Creating a commit
- A commit saves a change
- Has a clear title that explains what happened
- Can have a body (mostly used to explain why change was made)

---

# Creating a commit
## Add files to your commit
- Command: `git add {route to file}`


```sh
thibaut in ~/Projects/git-class-osoc
$ git add index.html
```

---

# Creating a commit
## After file is added
```sh
thibaut in ~/Projects/git-class-osoc
$ git status
#
# Changes to be committed:
# (use "git rm --cached <file>..." to unstage)
#
#	new file:   index.html
#
```
---

# Creating a commit
## Save your changes
```sh
git commit
```

```sh

# Please enter the commit message for your changes. Lines
# starting with '#' will be ignored, and an empty
# message aborts the commit.
#
# On branch master
#
# Initial commit
#
# Changes to be commited
# New file: index.html
#
```

---

# Creating a commit
## Save your changes
```sh
Creation of the homepage

This page will be the homepage of the site.

# Please enter the commit message for your changes. Lines
# starting with '#' will be ignored, and an empty
# message aborts the commit.
#
# On branch master
#
# Initial commit
#
# Changes to be commited
# New file: index.html
#
```

---

# Push commit
- Push new branch
```sh
thibaut in ~/Projects/git-class-osoc
$ git push --set-upstream origin master
```
- Push existing branch
```sh
thibaut in ~/Projects/git-class-osoc
$ git push
```

---

# Push commit
## Result
```sh
thibaut in ~/Projects/git-class-osoc
$ git commit
[master 0d2d4f2] Add title and body to commit
 1 file changed, 22 insertions(+)
```

---

# Flow visualization
![Flow visualization](/Users/thibautvincent/Projects/git-class-osoc/flowvisualization.png)

---

# Comitting
Only staged files are committed (`git add`)
```sh
thibaut in ~/Projects/git-class-osoc
$ git status

On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	flowvisualization.png

no changes added to commit (use "git add" and/or "git commit -a")
```

---

# Committing
#### Change last commit
`git commit --amend`
#### Write good commit messages
- English
- Present tense
### One commit is on change
- Don't fix bugs/ implement new features in 1 commit

---

# Committing
### Use git add patch
- `git add --patch` or `git add -p`
- Better control of what will be added to commit
- Make a habit of this one
