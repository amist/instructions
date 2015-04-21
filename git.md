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

You can see the status of the files in typing: `git status`

#### Untracked to Tracked ####

When a file is created or modified, it's in the **untracked** stage.

To add a file for the **tracked** stage:

`git add <filename or pattern>`

For example:

* Add a file: `git add readme.txt`
* Add a group of files: `git add *.txt`
* Add the whole directory (note the dot at the end): `git add .`

#### Tracked to Committed ####

After the file is in the list of the candidates for the commit, we need to *commit* it to the local repository.

To commit a file:

`git commit -m "<some comment>"`

#### Committed to Pushed ####

To push our local repository to github's repository, we need to push it:

`git push origin master`

If the remote server doesn't have your ssh keys, you'll be asked to enter a username and password.

---

Workflow
--------

#### Cloning a Repository ####

Let's say we have a github repository named `my_proj` stored in a github repository at `https://github.com/my_user/my_proj` and we want to have it on the directory `projects/my_proj`.

In `projects` directory we type:

`git clone https://github.com/my_user/my_proj`

#### Updating Changes from Others ####

`git pull origin master`

#### Pushing Our Changes ####

`git add <filename or directory>`

`git commit -m "<some comment"`

`git push origin master` 