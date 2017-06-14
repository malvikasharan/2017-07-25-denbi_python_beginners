# Teaching `git`

#### Setting Up Git

- How do I get set up to use Git?
  - __`git config`__
    - `git config --global user.name "Toby Hodges"`
    - `git config --global user.email "toby.hodges@embl.de"`
    - `git config --global color.ui "auto"`
- __`git clone`__
- (__`git init`__)
    - `cd my_project_repo`
    - `git init`
- Where does Git store information?
  - `ls -a -> .git`

#### `git status`

#### `git add`, `git commit`, `git commit -a`

- create a file
- `git status`
- `git add`
- `git status`
- `git commit -m "created file"`
- `git status`
- edit file
- create another file
- repeat above

- directories
  - `mkdir some_directory`
  - `git status`
  - `git add directory`
  - `git status`
  - add file to directory and repeat

#### ok, so what happened?

- __`git log`__
  - `git log -N`
  - `git log --oneline`
- show local repo figure
- explain terms
  - staging area
  - local repository

#### Exercise 1

#### Ignoring Things

- How can I tell Git to ignore files I don’t want to track?
  - `.gitignore`
  - start lines with `!` to negate earlier additions to file
  - `.gitkeep` has no special function, just for 

#### what's changed?

- __`git diff`__
  - `git add` + `git diff --staged`
  - `git diff --color-words` for word-wise instead of line-wise highlighting
- HEAD = most recent commit of the working directory
- `git diff HEAD drinks` == `git diff drinks`
- compare to older versions with `git diff HEAD~2`
- `git show HEAD~2 drinks`
- `git show <hashkey>` / `git show <shortkey>`

#### restoring old versions

- __`git checkout`__
  - `git checkout HEAD <file>` or `git checkout -- <file>` to discard uncommited changes to file
  - `git checkout HEAD~1` or `git checkout <hashkey>` (remember to use the key of the change you 
commited *before* the one you want to undo - this is a good reason to try to keep your changes/commits 
small and incremental)
  - `git checkout -f master <file>` to put things back to how they were
  - `git checkout <hashkey>` without file name => detached HEAD
  - fix with `git checkout master`
- how do you unstage changes?
  - `git reset HEAD <file>`

#### Exercise 2

#### Remotes in GitHub

- How do I share my changes with others on the web?
- create repo with same name on GitHub
  - SSH vs HTTPS
- `git remote add origin <repo-url>`
- `git push origin master`
- add README.md on GitHub
- `git pull origin master`
- edit something locally
- `git add`
- `git commit`
- `git push`

#### Collaborating - Exercise 3

- GitHub collab exercise (maybe this could go earlier?)
  - pair up - A and B
  - A adds B to A's project repository
  - B clones A's repository (somewhere else)
    - `git clone https://github.com/vlad/planets.git ~/Desktop/vlad-planets`
  - B makes a change, adds, commits, pushes to origin
  - check A's GH repo
  - A pulls changes
- whenever you start working on a project after a break, remember to `git pull` first
- diffs on github, comments/discussion
- `git blame <file>`
  - `git blame -L 40,60 <file>` = blame for lines 40-60

#### Conflicts - Exercise 4

- What do I do when my changes conflict with someone else’s?
- what's the most important git command?
  - `git status`
- pull, fix conflict, commit, push

#### Exercise 5 - repeat above

## Optional

#### More Collaborating

- branches
  - `git branch <branchname> && git checkout <branchname>` / `git checkout -b branchname`
  - create new file, add, commit
  - `ls`
  - `git checkout master`
  - `ls`
  - `git checkout <branchname>`
  - `git push origin <branchname>`
- pull/merge requests

#### Licensing

- What licensing information should I include with my work?
  - what it means if you don't include a license

#### Citation

- How can I make my work easier to cite?

#### Workflows

- `git-flow`
- GitHub flow

#### Hosting

- Where should I host my version control repositories?
