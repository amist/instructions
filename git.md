Git Instructions
================

---

Introduction
------------

When a new file is created or a file has been changed, it's going through four stages until the changes are mirrored in github:

* **Untracked:** the file is not a going to be commited in the next commit. 
* **Tracked:** the file is going to be commited in the next commit.
* **Committed:** the file is part of the local repository.
* **Pushed:** the file is part of github's repository.

You can see the status of the files in typing:

	git status

#### Untracked to Tracked ####

When a file is created or modified, it's in the **untracked** stage.

To add a file for the **tracked** stage:

	git add <filename or pattern>

For example:

* Add a file: `git add readme.txt`
* Add a group of files: `git add *.txt`
* Add the whole directory (note the dot at the end): `git add .`

#### Tracked to Committed ####

After the file is in the list of the candidates for the commit, we need to *commit* it to the local repository.

To commit a file:

	git commit -m "<some comment>"

#### Committed to Pushed ####

To push our local repository to github's repository, we need to push it:

	git push origin master

If the remote server doesn't have your ssh keys, you'll be asked to enter a username and password.

---

Workflow
--------

#### Cloning a Repository ####

Let's say we have a github repository named `my_proj` stored in a github repository at `https://github.com/my_user/my_proj` and we want to have it on the directory `projects/my_proj`.

In `projects` directory we type:

	git clone https://github.com/my_user/my_proj

#### Updating Changes from Others ####

	git pull origin master

#### Pushing Our Changes ####

	git add <filename or directory>
	git commit -m "<some comment>"
	git push origin master

---

Miscellaneous Actions
---------------------

All of the following commands are done inside the project's directory, unless noted otherwise.

### Revert ###

#### Revert the local repository to be like the origin repository ####
	git reset --hard origin/master

#### Revert the changes in the working copy to be like the local repository: ####
	git checkout .

#### Cancel 'git add' (untrack all the tracked files) ####
	git reset

---

### Show History ###
#### In the command line ####
	git log

#### In a GUI Interface ####
Git extensions need to be installed for the GUI interface. In windows it usually comes with the regular installation.

	gitk
 
---

### Show GUI for track, commit and push ###
	git gui


---

### Ignoring Files ###

It's best to ignore files before they being committed, because the repository stores every file that has ever been committed. Create or modify the file `.gitignore` to match the files you want to ignore. You can find example files [here](https://github.com/github/gitignore).

#### Ignore Committed Files ####
Edit the `.gitignore` file, then type:

	git rm -r --cached .
	git add .
	git commit -m "Update .gitignore"

---

### Tagging ###

Tagging is a way to mark a commit, making it easy to checkout that commit. Tags need to be push to the remote repository separately.

#### Tag ####
	git tag -a <tag name> -m "<tag comment>"

#### Push Tage to Remote Repository ####
	git push origin --tags

Tagging a commit other than the current one can be done easily with the GUI interface. Type `gitk`, then right click on the specific commit and choose `create tag`.

#### Delete a Tag ####
	git tag -d <tag name>

#### Delete a Tag from the Remote Repository ####
	git push origin :<tag name>

#### Recomment a Tag ####
	git tag <tag name> <tag name> -f -m "comment"

#### Switch to Tag ####
	git checkout tags/<tag name>

#### Switch to Master ####
	git checkout master

### Branching ###

#### Create a Branch ####
	git checkout -b <branch name>

Is equivalent to:

	git branch <branch name>
	git checkout <branch name>

#### Show The Current Branch ####
	git branch

#### Delete a Branch ####
	git branch -d <branch name> 

#### Delete a Branch from a Remote Repository ####
	git push origin --delete <branch name>

#### Merge a Branch into the Master ####
	git checkout master
	git merge <branch name>