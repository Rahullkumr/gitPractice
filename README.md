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

-----------------------------------

<img src="https://greater.nl/wp-content/uploads/2021/12/git.jpeg">

## GIT 

- git is a program that tracks changes made to a file
- git stands for global information tracker
- git is a distributed version control system
  >(other two are: localised vc (own laptop) and centralised vc (in an institute/company))
- `.git folder` inside a project, tracks all changes made over time,
  if you delete this folder the information of changes-made will be gone.

<img height=300 src="https://geo-python.github.io/site/2018/_images/Git_illustration.png">

## GIT WORKFLOW

1. Making changes
2. Staging changes
3. Commiting changes<br><br>

## STAGING AREA

- A concept in git, where the changes are stored before commiting

- The `index`(a binary file) inside `.git/` folder contains the changes added through staging


## GIT COMMIT

- Commits are stored in the `objects` folder in the `.git/` folder
- Each commit has a unique ID number or 'SHA'
	> each commit becomes a snapshot in that point of time which finaly forms a repo history

- If you made a typing error in the msg during commiting, then it can be corrected by the following:
	```
	git commit --amend -m 'typo corrected'
	```

## BRANCHING STRATEGIES

- The main idea behind branching is to isolate your work into different types of branches

- There are five different branch types in total:
	- Main / Master (outdated term)
	- Develop
	- Feature
	- Release
	- Hotfix
-------------------------------------------------------

<h1 align="center">GIT COMMANDS</h1>

## BASIC
- `git init` Initializes the folder for git commands
- `git clone url` copy a GitHub repo to local machine
- `git status` gives list of tracked(green) and untracked(red) files (staging area)
- `git add .` adds all files to staging area
- `git restore --staged filename.extension` remove from staging area
- `git commit -m 'must add message here'`  final save as snapshot

## GIT LOG
- `git log -5` gives detailed list of last 5 commits
- `git log --oneline` gives list of all commits in 1 line format
- `git log --oneline main..second_branch`
	- how far `second_branch` is ahead of the `main` branch
	- displays commits that are in `second_branch` but not in `main` branch 
	- > how far is main branch ==> just swap `second_branch..main`

## GIT BRANCH
- `git branch`  gives list of all branches
- `git branch branchName`  creates a new branch
- `git checkout branchName` go inside branchName
	> different branches for different features => because 1 branch allows only 1 pull request

## STASH AREA (like temp variable): 

	> a way to temporarily save uncommitted changes to working directory

	> useful if you need to switch branches but don't want to lose your changes	

	> You're working on a feature branch, but need to fix a master branch bug. Stash your feature branch changes, switch to master, fix the bug, switch back to feature branch, and apply stashed changes

	> You can stash your changes and then push the stash to the remote repository. Your teammates can then pop the stash and apply your changes to their working directories.

- `git stash` save to stash area (go backstage)
- `git stash list` view list of stashed files
- `git stash pop` come to front from backstage
- `git stash clear` clear stash area (clear backstage people)

<img height=300 src="https://i.imgflip.com/6rzn1t.jpg">

## GIT UNDOs

#### 1. REVERT

----------------------- `git revert hashvalue`
- `git revert HEAD` ➡ undo 1 commit after opening editor
- `git revert HEAD --no-edit` undo 1 commit without opening editor
	> used when we want to take a previous commit and add it as a new commit, keeping the log intact

#### 2. AMEND 

- `git commit --amend -m 'typo corrected'` correct spelling error of last commit

#### 3. RESET 

- `git reset hashvalue/commitvalue`
	> used to move the repository back to a previous commit, unstaging any changes made after that commit
- suppose it's Friday and you want to reset the branch as it was on Tuesday


## REMOTE

	> a reference to another Git repository. 
	It is a way to keep a copy of your repository on a different server.

	> a repo can have multiple remotes: To keep backup of the repository on different servers. 
	This way, if something happens to one server, you won't lose your work.

	> Use multiple remotes to keep your development, staging, and production environments separate. 
	Push changes to each environment independently.

- `git remote add remoteName url` (default = origin) creates a new remote entry in repository's `.git/config file`
- `git remote remove remoteName` deletes a remote
- `git remote -v` list all remotes along with their URL
- `git log --remotes` gives list of commits done from different REMOTES
> `git push remoteName branchName` push commits to the remote(ie GitHub) repository

## SYNCING COMMITS TO LOCAL 

> bring all commits made on the upstream to local repository 

#### 1. GIT FETCH

	> used to fetch changes (commits, branches, tags, etc.) from upstream without automatically merging or applying those changes to current local branch

- `git fetch --all --prune` 

	> --all => all branches and all remotes <br>
	> --prune => deleted also

- Options after fetching:

	> 1. Reset: `git reset --hard remoteName/branchName` reset the local branch with remote branch(LOCAL K SAARE COMMITS CHU MANTAR[very dangerous])

	> 2. Rebase: `git rebase origin/main` local branch gets rebased to remote branch "origin/main" (if no conflict else JHANJHAT)

	> 3. Merge: `git merge origin/main` local branch gets merged with remote branch "origin/main" (if no conflict else JHANJHAT)

	> 4. `git log --oneline main..second_branch` how far `second_branch` is ahead of the `main` branch.

#### 2. GIT PULL (RECOMMENDED)

- `git pull remoteName branchName` 

	> used to bring changes from remote repository and automatically merge them into local current branch
	> - Internally it does => "git fetch + git merge"

## SQUASHING 

- used to combine multiple commits into a single commit

- useful for feature branches where you might have made many small, incremental commits during development

- good to squash commits before creating a PR to maintain clean history for the main branch.
 
- steps:

 	- use log, note down hashvalue of to-be-combined commits

	- `git rebase -i HEAD~n` 
		> i = interactive mode i.e editor will open <br>
		> n = how many commits to be combined including HEAD(most recent commit)

	- new editor opens, change "pick" => squash but leave first one as it is, save and exit

	- new editor opens, give meaningful commit msg on first line, don't touch other lines, save and exit

	- REBASE success, if no conflicts present

	- force push to remote repo: `git push -f`



## GIT PUSH

#### 1. Normal Push

- `git push remoteName branchName` push commits to the remote(ie GitHub) repository


#### 2. Force Push
> [REMOTE K SAARE COMMITS CHU MANTAR, VERY DANGEROUS]

- `git push origin branchName -f`

	- Overwrites remote branch history with local branch history. 
	- This means that any commits on the remote branch that are not on the local branch will be deleted from the remote branch.
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
- difference b/w two commits ➡ only using GitHub
```