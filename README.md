# Git
Quick reference for basic git &amp; github commands


## Basic commands for standard git workflow

- `git status` - use this command if you want to check what changes git is tracking

- `git add FILENAME` - add file to the Staging Area

- `git add .` - this is variation of git add command, where we use wildcard. It means that we want every file to be added to our Staging Area.
  
- `git commit -m "MESSAGE"` - commit changes that are currently in the Staging Area. Remember :exclamation::exclamation: Always add commit message that will describe what changes you have made.
  
- `git commit` - this command will commit your changes. Here you will get a chance to write your commit message inside editor specified in config file. It is useful when you add more verbose messages to your commits.
  
- `git log` - show history of all commits. 
  
- `git show` - will display more detailed version of commits along with diffs.
  
**Back out changes**

- `git reset HEAD FILENAME` - use when you added something to the Staging Area by mistake. :o::o: Remember. Changes you made to that files will still be visible in your local repository. You just removed file from Staging Area.

- `git checkout -- FILENAME` - this command will be useful if you want to remove changes from Staging Area. Works for changes that are unstaged, so if you added changes to the Staging Area you have to use `reset` first.
  
**File Manipulations**

Always try to use git commands when renaming or deleting a file.

- `git mv OLDNAME NEWNAME` - this command let you rename a file with git.
  
- `git rm FILENAME` - that's how you remove file using git.

**Git Ignore**

- `.gitignore` - here we store files that we don't want to be tracked by git. This files won't be pushed to our remote repositories as well.


## Beyond Basics 


- `git diff COMMIT1 COMMIT2` - display differences between commits.

-  `git difftool COMMIT1 COMMIT2` - :+1: Preffered. Does exactly the same thing but uses  code editor insead of command line.

**Branching & Merging**

This is the main reason why we use git. 

Merge Types:
  
1. Fast Forward - simplest merge
2. Automatic Merge
3. Manual Merge - we manually solve conflits if git is unable to solve them automaticlly.

- `git branch` - displays current branch
  
- `git branch -a` - displays list of all branches

- `git checkout -b NEWBRANCH` - this command will create new branch inside of your project. If you changed files before changing the branch, those changes will be transferred to the new branch.

- `git checkout BRANCHNAME` - switch to another branch

- `git merge BRANCHNAME` - this will allow you to merge to branches. First go to your main branch and then use this command to merge it with your feature branch.
  
- `git mergetool` - uses mergetool to resolve conflits

**Conflits**

To create a conflit inside a git repository (at least that's how I understand this) you need to have to copies of the same file. Inside those files there will be two different texts. Git doesn't know which copy of the file you want to keep. So he will ask you about that.


**Creating aliases**

- `git config --global alias.ALIASNAME "COMMAND "` - this is pretty useful if we regularly use more complicated commands and we want to have an alternative and simpler way to do it.

