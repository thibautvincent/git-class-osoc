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
