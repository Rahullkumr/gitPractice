# Git notes

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


## Git: 
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
