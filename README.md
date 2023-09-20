<center><img alt = "Git Banner" src = "banner.png"></center>
<h4 align='center'>
	<a href = "https://github.com/Rahullkumr/gitPractice/blob/master/Coursera/test_qns.md">Git Coursera MCQ</a>
</h4>


## Basic Linux Commands: 

- `ls -la folderName` list of files and folders including hidden files inside folderName 
- `touch fileName.ext` create new file
- `mkdir folderName` create new folder
- `cd` go to Parent directory
- `cd directoryName` change directory
- `cd ..` go back one directory
- `pwd` print present working directory
- `rm fileName` ➡ delete file
- `rm  -r folderName` ➡ delete folder
- `cp file1.extnsn file2.extnsn` copy file1's content into file2 (OVERRIDES)
- `mv oldName.extn newName.extn` ➡ rename oldName to newName
- `mv file1.ext folder/lol.md` ➡ move file1 to folder as lol.md
- `cat file1` print content of file1
- `cat > file.ext` enter input & (ctrl+d and ctrl+d) to save and exit (OVERRIDES)
- `cat >> file.ext` enter input & (ctrl+d and ctrl+d) to save and exit (APPENDS)

## Basic Vim Commands

- `i` Enter insert mode
- `esc` exit insert mode
- `:wq ➡ Save and quit Vim`
- `:w` Save file
- `:q` Quit Vim editor
- `:q!` Quit Vim without saving


# Git: 
- git is a program that tracks changes made to a file
- git stands for global information tracker
- git is a distributed version control system
  >(other two are: localised vc (own laptop) and centralised vc (in an institute/company))
- .git folder inside a project, tracks all changes made over time,
  if you delete this folder the information of changes-made will be gone.

## Typical git workflow
1. making changes
2. Staging changes
3. commiting changes

## Staging area:

```
The /index folder inside the .git/ folder that contains the changes added through staging
```

# commit:
```
commits are stored in the /objects folder in the .git/ folder.
Each commit has a unique ID number or 'SHA'
```

### each commit becomes a snapshot in that point of time which finaly forms a repo history.

If you made a typing error in the message during commiting, then it can be corrected by the following:
```diff
git commit --amend -m 'typo corrected'
```

## diff:
``` git diff main.py app.py```
- takes two datasets and tells the difference between them. Dataset can be files, commits, brances or tags.
- added lines are highlighted as green and deleted as red

## Revert/undo a commit
```
git revert <commit>
git revert 45111a
```

## Git Branching Strategy

The main idea behind branching is to isolate your work into different types of branches.
There are five different branch types in total:

- Main / Master (outdated term)
- Develop
- Feature
- Release
- Hotfix

----
# Git Commands

`git init` Initialize the folder for git commands

`git clone url` copy a GitHub repo to local machine

`git status` gives list of tracked(green color) and untracked(red color) files i.e files inside and outside staging area

`git add .` adds all unstaged files to staging area
`git restore --staged filename.extension` remove from staged area

`git commit -m 'must add message here'`  final save as snapshot

`git log -5` gives latest 5 commit history
`git log --oneline` gives history of commits in brief in 1 line

`git log --oneline main..second_branch` display commits that are in `second_branch` but not in `main` branch 
➡ how far `second_branch` is ahead of the `main` branch.
> how far is main branch ==> just swap `second_branch..main`


`git branch branchName`  creates a new branch

`git checkout branchName` go inside branchName
> different branches for different features => because 1 branch allows only one pull request

STASH AREA (like temp variable): 

	> a way to temporarily save uncommitted changes to working directory
	> useful if you need to switch branches but don't want to lose your changes	
	> You're working on a feature branch, but need to fix a master branch bug. Stash your feature branch changes, switch to master, fix the bug, switch back to your feature branch, and apply your stashed changes.
	> You can stash your changes and then push the stash to the remote repository. Your teammates can then pop the stash and apply your changes to their working directories.

`git stash(like recycle bin)` go backstage

`git stash list` view list of stashed changes

`git stash pop` come to front from backstage

`git stash clear` clear backstage people


## GIT UNDOs

`git revert HEAD` ➡ go back one commit after opening editor

`git revert HEAD --no-edit` go back one commit without opening editor

	> REVERT is the command we use when we want to take a previous commit and add it as a new commit, keeping the log intact

`git reset hashvalue/commitvalue`

	> RESET is the command we use when we want to move the repository back to a previous commit, discarding any changes made after that commit
- go back to a particular commit, the commits after this hashvalue will be unstaged
- suppose it's Friday and you want to reset the branch as it was on Tuesday

`git commit --amend -m 'typo corrected'` correct spelling error of latest commit


`REMOTE`

	> A remote is a reference to another Git repository. It is a way to keep a copy of repository on a different server.
	> multiple remotes: To keep backup of your repository on a different servers. This way, if something happens to one server, you won't lose your work.
	> A developer might have a remote for their personal Git server and another remote for their work Git server. This would allow them to keep their personal projects and work projects separate.
	> Use multiple remotes to keep your development, staging, and production environments separate. Push changes to each environment independently.

`git remote add remoteName url` (default = origin) create a new remote entry in repository's .git/config file.

`git remote remove remoteName` delete a remote

`git remote -v` lists all remotes along with their URLs

`git log --remotes` list of commits done from different REMOTES


`git push remoteName branchName` push committed changes to the GitHub repository

## Sync (bring) all commits made on the upstream to local repository 

* GIT FETCH
- used to fetch changes (commits, branches, tags, etc.) from upstream without automatically merging or applying those changes to current local branch.

`git fetch --all --prune` 

> --all => all branches and all remotes
> --prune => deleted also

- Options after fetching:
	> 1. Reset: `git reset --hard remoteName/branchName` reset the local branch with remote branch(LOCAL K SAARE COMMITS CHU MANTAR[very dangerous])
	> 2. Rebase: `git rebase origin/main` local branch gets rebased to remote branch "origin/main" (if no conflict else JHANJHAT)
	> 3. Merge: `git merge origin/main` local branch gets merged with remote branch "origin/main" (if no conflict else JHANJHAT)
	> 4. `git log --oneline main..second_branch` how far `second_branch` is ahead of the `main` branch.


* GIT PULL (RECOMMENDED)
`git pull remoteName branchName` 
- used to fetch changes from remote repository and automatically merge them into local current branch
> Internally it does => "git fetch then git merge"

## SQUASHING 
- used to combine multiple commits into a single
- useful for feature branches where you might have made many small, incremental commits during development
- good to squash commits before creating a PR to maintain clean history for the main branch.
 
 steps:
 
	- use log, note down to-be-changed commits hash
	- `git rebase -i HEAD~n` i=interactive n=how many commits including HEAD(most recent commit)
	- new editor opens, change "pick" => squash but leave first as it is, save and exit
	- new editor opens, give meaningful commit msg on first line only, don't touch other lines, save and exit
	- REBASE success, if no conflicts present
	- force push to remote repo: `git push -f`



## Force Push 
> [REMOTE K SAARE COMMITS CHU MANTAR, VERY DANGEROUS]

`git push origin branchName -f`

- Overwrites remote branch's history with local branch's history. This means that any commits on the remote branch that are not on the local branch will be deleted from the remote branch.
- very useful, Removing a commit from the pull request

```diff
- merge vs rebase (two ways of Integration)
+ merge makes commit history dirty
+ rebase keeps commit history clean

- merge conflict
+ multiple people modified same line and requested for pull request 

- resolve merge conflict ➡ only using GitHub
- Pull Request ➡ only using GitHub
- fork a repository ➡ only using GitHub

```