# Mastering Git
This project is used to demonstrate some lesser known git commands.

### Configuring the default editor for git messages
By default git uses your system default editor. To change it to something with an UI, for example, you can configure it as such
```bash
git config --global core.editor sunl
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