+++
Categories = ["Spotlights and Solutions"]
Tags = []
date = "2015-07-21T22:05:06-07:00"
title = "Git Hacks - WIP Edition"

+++

Today's post is about some quick `git` command line tricks if you are doing some work in progress (WIP). 

Scenario: You are working on the `master` branch and then realize you are going to have to test these changes on a bigger scale (perhaps cross repo) and thus new to push your changes to a new branch. 

Setup: On master branch, some `git add` have been made, no commits yet. 

Solution: 

First, remove all the staged files from the master branch. Use `git rm --cached` and then either add the file path or the directory path to be removed. You can use `git status` to find out what files are not staged yet. For example:

```bash
# Originally, everything is up to date
# but on the wrong branch 
git status 
On branch feature-branch
Your branch is up to date with origin/master
nothing to commit, working directory clean 

# Remove those files 
git rm --cached foo/
git rm --cached bar/foo.java

# Good, ready to be added to another branch
git status 
Changes not staged for commit:
	modified: foo/
Untracked files:
	bar/foo.java
```

Make sure to have the `--cached` flag because that means that you are removing the file from the git index to reset the tracking but not the actual file from your local file system. You don't want that, because you are about to push these changes to another branch. 

Second, checkout a new branch. The cool thing is that the current state of files follows you to the current branch. Then, push to remote repo, setting up tracking to be from the origin (usual use case). 

```
git checkout -b feature-branch
git add .
git commit -m "Pushing changes to local feature branch"
git push -u origin feature-branch
```

The last command, `git push -u origin feature-branch` sets up the remote branch to track changes from. In the future, you only need to write `git push -u feature-branch` and your changes will be pushed to the remote branch of the same name as your local branch. 


### Sources

* [Pushing uncommitted changes to a new branch](http://stackoverflow.com/questions/1351567/putting-uncommitted-changes-at-master-to-a-new-branch-by-git)
* [Using git rm --cached ](http://stackoverflow.com/questions/7434449/why-use-git-rm-to-remove-a-file-instead-of-rm
)