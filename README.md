# gitPractice

Its the first time that i am working with CMD for git commands.
I am using CMD as well as Git Bash.

I am enjoying it.

I think its only "git push" Not "git push origin master".

No, you have to give the full command "git push remoteName branchName".
Otherwise that will not be accepted.

Final and the genuine answer: You don't have to give "origin master" if it's a cloned repository from 
GitHub because "git clone" automatically adds the remote "origin".
If u have a local folder and transformed it to Repo then that is necessary.


## Practice makes everyone perfect.

About "git commit"
	You have to use "-a" and -m "commit message" if the file being worked is not added to staging area
where
	-a = for all files in the working directory
	-m = for the commit message or comment

If u wanna add only few files to the repository,then add those to the staging area.
By using " git add" command and finally commit.

---

# Introduction to Git and GitHub (Coursera/Google)
This file contains all the mcq that were asked in the Coursera Course.

<details>
	<summary>
		<h2>Module 1</h2>
	</summary>
	
1. Your colleague sent you a patch called fix_names.patch, which fixes a config file called fix_names.conf. What command do you need to run to apply the patch to the config file?

```diff
'diff names.conf fix_names.conf 
'patch fix_names.conf names.conf 
+ patch fix_names.conf < fix_names.patch
'diff names.conf_orig names.conf_fixed > fix_names.conf
```

2. You're helping a friend with a bug in a script called fix_permissions.py, which fixes the permissions of a bunch of files. To work on the file, you make a copy and call it fix_permissions_modified.py. What command do you need to run after solving the bug to send the patch to your friend?

```diff
+ diff fix_permissions.py fix_permissions_modified.py > fix_permissions.patch
 patch fix_permissions.py < fix_permissions_modified.py
 patch fix_permissions.py > fix_permissions.patch
 diff fix_permissions.py fix_permissions.diff
```

3. The _____ command highlights the words that changed in a file instead of working line by line.

```diff
 diff
 diff -u
+ wdiff
 patch
```

4. How can we choose the return value our script returns when it finishes?

```diff
+ Using the exit command from the sys module
Use the patch command
Use the diff command 
Use meld
```

5. In addition to the original files, what else do we need before we can use the patch command?

```diff
+ Diff file
exit command of the sys module
Version control
Full copy of the new files
```

6. How can a VCS (Version Control System) come in handy when updating your software, even if you’re a solo programmer? Check all that apply.

```diff
Git retains local copies of repositories, resulting in fast operations.
+ If something breaks due to a change, you can fix the problem by reverting to a working version before the change.
+ Git relies on a centralized server.
+ Git allows you to review the history of your project.
```

7. Who is the original creator and main developer of the VCS (Version Control System) tool Git?

```diff
Bill Gates
Guido van Rossum
+ Linus Torvalds
James Gosling
```

8. _____ is a feature of a software management system that records changes to a file or set of files over time so that you can recall specific versions later.

```diff
A repository
sys.exit()
+ Version control
IDE
```

9. A _____ is a collection of edits which has been submitted to the version control system for safe keeping.

```diff
IDE
version control system
+ commit
repository
```

10. Within a VCS, project files are organized in centralized locations called _____ where they can be called upon later.

```diff
commits
+ repositories
IDE
yum
```

11. Before changes in new files can be added to the Git directory, what command will tell Git to track our file in the list of changes to be committed?

```diff
git status
+ git add
git commit 
git init
```

12. Which command would we use to review the commit history for our project?

```diff
git clone
git status
git config -l
+ git log
```

13. What command would we use to make Git track our file?

```diff
git clone
git status
+ git add
git log
```

14. Which command would we use to look at our config?

```diff
git clone
git status
+ git config -l
git log
```

15. Which command would we use to view pending changes?

```diff
git clone
+ git status
git config -l
git log
```
</details>










<details>
	<summary>
		<h2>Module 2</h2>
	</summary>
	

1. Which of the following commands is NOT an example of a method for comparing or reviewing the changes made to a file?

```diff
git log -p
git diff --staged
git add -p
+ git mv
```

2. What is the gitignore file?

```diff
A file containing a list of commands that Git will ignore.
A file the user is intended to ignore.
A file listing uncommitted changes.
+ A file containing a list of files or filename patterns for Git to skip for the current repo.
```

3. What kind of file will the command git commit -a not commit?

```diff
Tracked files
+ New files
Old files
Staged files
```

4. What does HEAD represent in Git?

```diff
The subject line of a commit message
The top portion of a commit
+ The currently checked-out snapshot of your project
The first commit of your project
```

5. If we want to show some stats about the changes in a commit, like which files were changed and how many lines were added or removed, what flag should we add to git log?

```diff
+ --stat
 --patch
 -2
 --pretty
```

6. Let's say we've made a mistake in our latest commit to a public branch. Which of the following commands is the best option for fixing our mistake?

```diff
+ git revert
git commit --amend
git reset
git checkout -- <file>
```

7. If we want to rollback a commit on a public branch that wasn't the most recent one using the revert command, what must we do?

```diff
Use the git reset HEAD~2 command instead of revert
Use the revert command repeatedly until we've reached the one we want
+ use the commit ID at the end of the git revert command
Use the git commit --amend command instead
```

8. What does Git use cryptographic hash keys for?

```diff
To secure project backups
To guarantee the consistency of our repository
To encrypt passwords
+ To identify commits
```

9. What does the command git commit --amend do?

```diff
Start a new branch
Create a copy of the previous commit
Delete the previous commit
+ Overwrite the previous commit
```

10. How can we easily view the log message and diff output the last commit if we don't know the commit ID?

```diff
+ git show
git identify
git log
git revert 
```

11. When we merge two branches, one of two algorithms is used. If the branches have diverged, which algorithm is used?

```diff
+ three-way merge
fast-forward merge
merge conflict
orphan-creating merge

```

12. The following code snippet represents the result of a merge conflict. Edit the code to fix the conflict and keep the version represented by the current branch.

```diff
+ print("Keep me!")
```

13. What command would we use to throw away a merge, and start over? 

```diff
git checkout -b <branch>
+ git merge --abort
git log --graph --oneline 
git branch -D <name>
```

14. How do we display a summarized view of the commit history for a repo, showing one line per commit? 

```diff
git log --format=short 
git branch -D <name>
+ git log --graph --oneline 
git checkout -b <branch>
```

15. The following script contains the result of a merge conflict. Edit the code to fix the conflict, so that both versions are included.

```diff
+ def main():
+     print("Start of program>>>>>>>")
+     print("End of program!")
+ main()
```
</details>










<details>
	<summary>
		<h2>Module 3</h2>
	</summary>
	
1. When we want to update our local repository to reflect changes made in the remote repository, which command would we use?

```diff
git clone <URL>
git push
+ git pull
git commit -a -m
```

2. git config --global credential.helper cache allows us to configure the credential helper, which is used for ...what?

```diff
Troubleshooting the login process
Dynamically suggesting commit messages
Allowing configuration of automatic repository pulling
+ Allowing automated login to GitHub
```

3. Name two ways to avoid having to enter our password when retrieving and when pushing changes to the repo. (Check all that apply)

```diff
Implement a post-receive hook
+ Use a credential helper
+ Create an SSH key-pair
Use the git commit -a -m command.
```

4. Before we have a local copy of a commit, we should download one using which command? 

```diff
git commit -a -m
git push
git pull
+ git clone <URL>
```

5. In order to get the contents of a remote branch without automatically merging, which of these commands should we use?

```diff
git pull
+ git remote update
git checkout
git log -p -1
```

6. If we need to find more information about a remote branch, which command will help us?

```diff
git fetch
git checkout
git remote update
+ git remote show origin
```

7. What command will download remote branches from remote repositories without merging the content with your current workspace automatically?

```diff
git checkout
git pull
+ git fetch
git remote update
```

8. What type of merge creates a new merge commit?
```diff
Fast-forward merge
Implicit merge
+ Explicit merge
Squash on merge
```

9. What method of getting remote contents will automatically merge the remote branch with the current local branch?

```diff
git fetch
git checkout
git remote update
+ git pull
```

10. If you’re making changes to a local branch while another user has also made changes to the remote branch, which command will trigger a merge?

```diff
git push
+ git pull
git rebase
git fetch
```

11. Which of the following is a reason to use rebase instead of merging? 

```diff
+ When you want to keep a linear commit history
When you want a set of commits to be clearly grouped together in history
When you are on a public branch
When pushing commits to a remote branch
```

12. Where should we keep the latest stable version of the project?

```diff
The master branch
+ A separate branch from the master branch
The debug branch
A remote branch 
```

13. Which of the following statements represent best practices for collaboration? (check all that apply)

```diff
+ When working on a big change, it makes sense to have a separate feature branch.
You should always rebase changes that have been pushed to remote repos.
+ Always synchronize your branches before starting any work on your own.
+ Avoid having very large changes that modify a lot of different things.
```

14. What command would we use to change the base of the current branch?

```diff
git checkout <branchname>
git pull
+ git rebase <branchname>
git fetch
```
</details>










<details>
	<summary>
		<h2>Module 4</h2>
	</summary>
	
1. What is the difference between using squash and fixup when rebasing?

```diff
Squash deletes previous commits.
+ Squash combines the commit messages into one. Fixup discards the new commit message.
Squash only works on Apple operating systems.
Fixup combines the commit messages into one. Squash discards the commit message.
```

2. What is a pull request?

```diff
The owner of the target repository requesting you to add your changes.
+ A request sent to the owner and collaborators of the target repository to pull your recent changes.
A request to delete previous changes.
A request for a specific feature in the next version.
```

3. Under what circumstances is a new fork created?

```diff
+ When you want to experiment with changes without affecting the main repository.
When you clone a remote repository to your local machine.
During a merge conflict.
When there are too many branches.
```

4. What combination of command and flags will force Git to push the current snapshot to the repo as it is, possibly resulting in permanent data loss?

```diff
+ git push -f
	> git push with the -f flag forcibly replaces the old commits with the new one and forces Git to push the current snapshot to the repo as it is. This can be dangerous as it can lead to remote changes being permanently lost and is not recommended unless you're pushing fixes to your own fork (nobody else is using it) such as in the case after doing interactive rebasing to squash multiple commits into one as demonstrated.
git log --graph --oneline --all
git status 
git rebase -i
```

5. When using interactive rebase, which option is the default, and takes the commits and rebases them against the branch we selected?

```diff
squash
edit
reword
+ pick
```
6. When should we respond to comments from collaborators and reviewers?

```diff
When their comments address software-breaking bugs
No need, just resolve the concerns and be done with it
+ Always
Only when a code correction is necessary
```

7. What is a nit?

```diff
+ A trivial comment or suggestion
A couple lines of code
A repository that is no longer maintained
An orphaned branch
```

8. Select common code issues that might be addressed in a code review. (Check all that apply)

```diff
+ Using unclear names
Following PEP8 guidelines
+ Forgetting to handle a specific condition
+ Forgetting to add tests
```

9. If we've pushed a new version since we've made a recent change, what might our comment be flagged as?

```diff
Accepted
Resolved
+ Outdated
Merged
```

10. What are the goals of code review? (Check all that apply)

```diff
+ Make sure that the contents are easy to understand
+ Ensure consistent style
Build perfect code
+ Ensure we don't forget any important cases
```


11. How do we reference issues in our commits with automatic links?

```diff
+ By using one of the keywords followed by a hashtag and the issue number.
By using an asterisk (*) after the issue number.
By typing the issue number inside braces ({}).
By using a special keyword.
```

12. What is an artifact in terms of continuous integration/continuous delivery (CI/CD) pipelines?

```diff
An old and obsolete piece of code or library.
+ Any file generated as part of the CI/CD pipeline.
An unintended minor glitch in a computer program
An automated series of tests that run each time there is a new commit or pull request.
```

13. Which of the following statements are good advice for project maintainers? (Check all that apply)

```diff
Coordinate solely via email
+ Reply promptly to pull-requests
+ Understand any changes you accept
+ Use an issue tracker 
```

14. Which statement best represents what a Continuous Integration system will do?

```diff
+ Run tests automatically
Update with incremental rollouts
Assign issues and track who's doing what
Specify the steps that need to run to get the result you want
```

15. Which statement best represents what a Continuous Delivery (CD) system will do?

```diff
Run tests automatically
+ Update with incremental rollouts
Assign issues and track who's doing what
Specify the steps that need to run to get the result you want
```
</details>



