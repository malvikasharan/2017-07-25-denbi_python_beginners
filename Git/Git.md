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
Verify that it is indeed a repository
```{bash}
git status
```
## Tracking Changes
Create a file called `mars.txt`
```{bash}
nano mars.txt
```
and enter the following text
```
Cold and dry, but everything is my favorite color
```
Verify that git noticed some changes with
```{bash}
git status
```
Add the changes to the staging area
```{bash}
git add mars.txt
```
Again check with
```{bash}
git status
```
Now commit the changes to the repository and provide a message
```{bash}
git commit -m "Start notes on Mars as a base"
```
Re-check `git status`.
Have a look in the log
```{bash}
git log
```
We will now introduce some changes. Open the file again with `nano mars.txt` and add a second line
```
The two moons may be a problem for Wolfman
```
Use `git status` again.
To see the introduced changes use
```{bash}
git diff
```
Add and commit the new content
```{bash}
git add mars.txt
git commit -m "Add concerns about effects of Mars' moons on Wolfman"
```
Repeat the above steps as often as you want.
You can check your commits with `git log` at any time.