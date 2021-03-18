# Git Merge

## Merge Exercise

- Create a new local repository

```
cd ~/Developer
mkdir git-merge-training
cd git-merge-training
git init
```

- Create a first commit

```
touch first-file
git add first-file
git commit
```

- Create and checkout a new branch

```
git branch feature-branch-a
git checkout feature-branch-a
```

- Now add a new line to first-file and commit it, e.g. 'Change from Feature A'
- Afterwards jump back to master and from there create yet another branch

```
git checkout master
git branch feature-branch-b
git checkout feature-branch-b
```

- Add a different line to the empty first-file and commit it, e.g. 'Change from Feature B'

- Now it's time to merge, let's start with a Fast Forward Merge. Jump to master and merge in feature-branch-a

```
git checkout master
git merge feature-branch-a
```

This merge should happen automatically. Verify that we just forwarded master to match feature-branch-a with git log. Here are some more command line options to get a clerer overview of the graph

```
git log --graph --oneline --all
```

The next merge should result in a merge conflict. We'll try to get the changes from feature-branch-b into the master branch

```
git merge feature-branch-b
```

This is the output you should see

```
Auto-merging first-file
CONFLICT (content): Merge conflict in first-file
Automatic merge failed; fix conflicts and then commit the result.
```

If you run git status you can always get a better overview. It is telling us that there are merge conflicts in `first-file`
If we open the file it looks something like this

```
<<<<<<< HEAD
Change from Feature A
=======
Change from Feature B
>>>>>>> feature-branch-b
```

Now you have to manually edit this file to decide which changes you like, for example you could just keep both. But really it's up to you to fix the conflicts in whatever way makes sense

```
Change from Feature A
Change from Feature B
```

or maybe

```
Change from Feature A and B
```

To finalize the merge add and commit

```
git add first-file
git commit
```

Now repeat all these steps multiple times until you get the hang of it.

## Git Step By Step Guides

### Creating a new feature and publishing it to create a pull request

First checkout master and sync it with the latest version on the remote origin

```
git checkout master
git pull
```

Then branch of by creating a new branch and checking it out

```
git branch my-feature
git checkout my-feature
```

These commands can be combined like this

```
git checkout -b my-feature
```

Now you can freely add and commit

```
git add .
git commit -m "Add a new feature
```

If while you are working on your feature new changes have been added to the master branch you can get them into your local branch like this:

```bash
# Download the newest version of origin/master (and all the other remote branches)
git fetch --all
# Merge the changes from origin/master into your local feature branch (the branch you are currently sitting on)
git merge origin/master
```

If you are ready to publish your changes to create a pull request on github, you have to push your feature branch to the origin with the following command

```bash
git push -u origin my-feature
# origin is the name of the remote to push to
# my-feature is the name of the branch to create/update on the remote
# -u stands for set-upstream which will connect your local branch my-feature with the remote version my-feature as its default push and pull traget
```

### Resolving merge conflicts

Scenario: You are merging with another branch, but automatic merging failed and you are left with some merge conflicts marked in the different files.

First run git status to get an idea of where merge conflicts have been found

```
git status
```

Next open the first file with a merge conflict and look for the marks `>>>>>>>>>>>` and `<<<<<<<<<<<<` which show you where merge conflicts have happened.

Decide which changes you want to use and edit the file (remove the marks)

If you have resolved all merge conflicts in this file you can mark it as resolved with git add

```
git add path/to/file-with-merge-conflicts.js
```

Continue until when you run git status there are no more files marked as containing merge conflicts

Then you are ready to complete the merge by running git commit. The commit message will already be prefilled with the name of the branch you merged in. You can keep this default merge commit message, but also feel free to change it to add more specific details

```
git commit
```
