# Git
See also:
 - https://swcarpentry.github.io/git-novice
 - http://rogerdudler.github.io/git-guide/
## Setup
Set global configuration
```{bash}
git config --global user.name "Vlad Dracula"
git config --global user.email "vlad@tran.sylvan.ia"
git config --global color.ui "auto"
```
List all configured values
```{bash}
git config --list
```
## Creating a Repository
First we create a new directory, then we initialize it as a repository
```{bash}
mkdir planets
cd planets
git init
```
Now you can verify that it is indeed a repository
```{bash}
git status
```
