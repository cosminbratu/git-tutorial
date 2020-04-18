
# Mastering Git
This project is used to demonstrate some lesser known git commands.

### Configuring the default editor for git messages
By default git uses your system default editor. To change it to something with an UI, for example, you can configure it as such
```bash
git config --global core.editor subl
```
### Cloning repos
The basic command is
```bash
git clone https://github.com/cosminbratu/git-tutorial.git
```
It clones the ```master``` branch of the repo and stores the changes in a folder with the same name as the repo ```git-tutorial```.
If you want a different branch, you use the ```-b``` argument
```bash
git clone -b my-other-branch https://github.com/cosminbratu/git-tutorial.git
```
If you want to specify a different output folder
```bash
git clone -b my-other-branch https://github.com/cosminbratu/git-tutorial.git git-tutorial-my-other-branch
```
### Short status
We often use the status command to show the stage contents, but it's pretty verbose
```bash
git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	new_file

no changes added to commit (use "git add" and/or "git commit -a")
```
There is a short version, called by ```--short (or -s)```. This displays the files along with symbols for denoting the different stages
```bash
git status -s
 M README.md
?? new_file
```
The left hand side is a two letter code and the common ones are:
- M - modified
- A - added
- D - deleted
- ?? - untracked
- ' ' - unmodified

### Ignore lists
By default, git tracks all files in a given repo. You can tell it to exclude different files by creating a ```.gitignore``` file in the root.
For a very good general starting point of git ignore files, you can use the GitHub collection of useful templates found at: https://github.com/github/gitignore.

### Skipping the staging area
You usually add/remove the files you want to commit and then call the ```git commit``` command. This is a two step command. If you know that you want to commit all tracked files, you can run
```bash
git commit -a -m "I'm sure it works"
```
<<<<<<< HEAD
and git adds everything to the staging area and then performs the commit.

### Tags
Tags are usually used to mark important points in the lifetime of projects, usually releases. We usually create annotated tags, being at the head of the branch
```bash
git tag -a v1.0 -m "Release 1.0"
```
Tags are not pushed to remote servers by default. We have to do it manually
```bash
git push origin v1.0
```
But if you passed the commit you wanted to tag (or you forgot), you can easily tag past commits
```bash
git tag -a v1.2 commit_sha
```
and git adds everything to the staging area and then performs the commit.
