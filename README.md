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
$ git config --global user.name "Thibaut Vincent"
$ git config --global user.email thibautvincent@icloud.com
```

---

# GIT GUI's (not recommanded)
- Some very basic GUIS
- Other Git GUIs also exist
	- Windows: Sourcetree, TortoiseGit, SmartGit, etc.
	- OS X: Sourcetree, Tower (paid), etc.

---

# Repositories
- The purpose of Git is to manage a project, or a set of files, as they change over time. Git stores this information in a data structure called a repository.

- A git repository contains, among other things, the following:

	- A set of commit objects.
	- Branches

---

## Creating repository
### Start tracking files in a directory with
	$ git init

### Autocreation of `.git` folder
- Meta information
- History
- Hooks (pre-commit checking, etc)
- ...

---

#### Example
```sh
thibaut in ~/Projects/git-class-osoc
$ git init
Initialized empty Git repository in
/Users/thibautvincent/Projects/git-demo/.git/
```

---

# Remotes
- A repository can be synched with a server
	- In Git this is called a remote
	- A remote is identified by a name, defaulting to origin, and a URL
	- Keep a local copy in sync with the remote by pushing and pulling
	- Several users can push/pull to/from the same remote

---

## Add a remote

---

### If a local copy of a repository doesn't exist yet
A local copy of the master + the entire commit history is created

```sh
thibaut in ~/Projects/git-class-osoc
$ git clone git@github.com:thibautvincent/git-class-osoc.git
```

---

### If a local copy of a repository already exists
If the remote repository is empty, push your master to it
```sh
thibaut in ~/Projects/git-class-osoc
$ git remote add origin git@github.com:thibautvincent/git-class-osoc.git

thibaut in ~/Projects/git-class-osoc
$ git push origin master
```

---

## Push and pull
### Publish locally committed changes
	$ git push origin master

### Pull changes from the server
	$ git pull
    or
    $ git pull origin {branch}

---

# Branching
- The entire commit history can be visualized as a timeline
![](/Users/thibautvincent/Projects/git-class-osoc/branch-history.png)

- This timeline is also called a branch
![](/Users/thibautvincent/Projects/git-class-osoc/master-branch.png)

---

- Default branch `master`
- List all branches
	`$ git branch`
- Create other branches to develop experimental features
	`$ git branch this-is-my-new-branch`
    This is local. You have to push your new branch before anyone else can see it

- Activate (checkout) a branch
	`$ git checkout this-is-my-new-branch`


---

# Branching off
Create a new branch from another branch
```sh
thibaut in ~/Projects/git-class-osoc
$ git branch
* master

thibaut in ~/Projects/git-class-osoc
$ git branch this-is-my-new-branch

thibaut in ~/Projects/git-class-osoc
$ git branch
  this-is-my-new-branch
* master

thibaut in ~/Projects/git-class-osoc
$ git checkout this-is-my-new-branch
Switched to branch 'this-is-my-new-branch'

```

---

## How does it looks like

---

![](/Users/thibautvincent/Projects/git-class-osoc/git-branching-1.png)

---

![](/Users/thibautvincent/Projects/git-class-osoc/git-branching-2.png)

---

![](/Users/thibautvincent/Projects/git-class-osoc/git-branching-3.png)

---

## Publishing/pulling branches
### Publish a branch
	$ git push origin localbranch:remotebranch`
### Update remote branch list
	$ git remote update
### Fetch all remote branches
	$ git fetch origin

---

# Committing

---

## Creating a commit
- A commit saves a change
- Has a clear title that explains what happened
- Can have a body (mostly used to explain why change was made)

---

## Check the status
Git compares the current state to the last state stored in the history

```sh
thibaut in ~/Projects/git-class-osoc
$ git status
#
# Untracked files:
#	index.html
#
```

---

### Add files to your commit
Before creating a commit, you have to add changes

```sh
thibaut in ~/Projects/git-class-osoc
$ git add index.html
```

---

### After file is added
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

### Save your changes

	$ git commit

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

### Add info to your commit
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

### Push commit
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

### Result
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

Only staged files are committed
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

#### Change last commit
	git commit --amend
#### Write good commit messages
- English
- Present tense
### One commit is on change
- Don't fix bugs/ implement new features in 1 commit

---

### Patching
- `git add --patch` or `git add -p`
- Better control of what will be added to commit
- Make a habit of this one

---

### Added file by accident?
	git reset index.html

### Compare the current state with the previously committed state
	git diff index.html

---

# History
```sh
thibaut in ~/Projects/git-class-osoc
$ git log
commit c53f9b6bd0e7271af7c5d856f84f51d9b749d77f
Author: Thibaut <thibautvincent@icloud.com>
Date:   Tue Mar 19 22:09:32 2013 +0100

    Hello

commit 1d7a18481b5f6664d2cf30b1455c6ad1c041caa2
Author: Thibaut <thibautvincent@icloud.com>
Date:   Tue Mar 19 21:24:13 2013 +0100

    Deleted test2.txt
```

---

### Summary
#### Create repository
	$ git init
#### Stage file
	$ git add file
### Unstage file
	$ git reset file

---
#### Commit staged changes
	$ git commit
#### Check differences in a file (compared to repository)
	$ git diff file
####  Check history
	$ git log

---

## Head
- The head is a reference to a commit object. Mostly this will be the latest commit
- After every commit the head will change to the latest commit
![](/Users/thibautvincent/Projects/git-class-osoc/git-timeline-master-head.png)

---

## Moving the head
	$ git checkout {commitId}
```sh
thibaut in ~/Projects/git-class-osoc
$ git log
commit c53f9b6bd0e7271af7c5d856f84f51d9b749d77f
Author: Thibaut <thibautvincent@icloud.com>
Date:   Tue Mar 19 22:09:32 2013 +0100

    Hello

commit 1d7a18481b5f6664d2cf30b1455c6ad1c041caa2
Author: Thibaut <thibautvincent@icloud.com>
Date:   Tue Mar 19 21:24:13 2013 +0100

    Deleted test2.txt
```

---

- Checking out to the desired commit

```sh
thibaut in ~/Projects/git-class-osoc
$ git checkout c53f9b6bd0e7271af7c5d856f84f51d9b749d77f
Note: checking out 'c53f9b6bd0e7271af7c5d856f84f51d9b749d77f'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.

HEAD is now at c53f9b6bd0e7271af7c5d856f84f51d9b749d77f... Deleted test2.txt
```

---

# Tips and tricks

---

## Gitignore
- Never commit config files!
- Add them to .gitignore
```
Thumbs.db
app.db
*.log
vendor/*
node_modules/*
config.php
```

---

## Partly staging files
```
bramus in ~/ikdoeict/ikdoeict-website on master*
$ git add -p index.html
diff --git a/index.html b/index.html
index 3fc8413..d7af84e 100644
--- a/index.html
+++ b/index.html
@@ -1,6 +1,6 @@
 <!DOCTYPE html>
 <head>
-	<title>Title</title>
+	<title>Home | Homepage</title>
	<meta charset="utf-8" />
	<link rel="stylesheet" href="css/normalize.css" />
Stage this hunk [y,n,q,a,d,/,j,J,g,e,?]? y


 ```

---

## Not enough?
Make sure you also check
- Stashing
- Tagging
- Cherry Picking
- Commit hooks

---

# Sources
- http://bramus.github.io/ws2-sws-course-materials
- http://learn.github.com/
- https://git-scm.com/
