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
```terminal
thibaut in ~/Projects/git-demo
$ git init
Initialized empty Git repository in /Users/thibautvincent/Projects/git-demo/.git/
```

---

# Working on existing files in repository
- Start working on files
 `git clone git@github.com:thibautvincent/git-class-osoc.git`

---
