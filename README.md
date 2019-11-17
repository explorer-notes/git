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

- `git branch` - displays list of local branches
  
- `git branch -a` - displays list of all branches (local & remote)

- `git checkout -b NEWBRANCH` - this command will create new branch inside of your project. If you changed files before changing the branch, those changes will be transferred to the new branch.

- `git checkout BRANCHNAME` - switch to another branch.

- `git merge BRANCHNAME` - this will allow you to merge to branches. First go to your main branch and then use this command to merge it with your feature branch.
  
- `git mergetool` - uses mergetool to resolve conflits.

- `git branch -d BRANCHNAME` - removes branch from local repository.

**Conflits**

To create a conflit inside a git repository (at least that's how I understand this) you need to have to copies of the same file. Inside those files there will be two different texts. Git doesn't know which copy of the file you want to keep. So he will ask you about that.

**Tagging**

Tags are just labels you can add to your important commit points.

- `git tag TAGNAME` -adds tag to your current commit
  
- `git tag --list` - displays list of all tags

- `git tag -d TAGNAME` - use this if you want to delete tag

- `git tag -a VERSION -m "MESSAGE"` - letter `a` signals that it's annotated tag. With this tag we also add a message that relates to it. It's is useful to use this tag when you want to mark important moments in your project called **milestones.**

- `git show TAGNAME` - use this command if you want to see commit message that was attached to the annotated flag.

**Stashing**
Stashing is another important concept that lets you save your work in progress. It's useful when you want to switch context between branches without committing the changes that you made.

- `git stash` - saves changes made to the working directory.

- `git stash --list` - displays list of your stashes.

- `git stash pop` - this command will apply changes that were stashed in the working directory. After this command stash will be removed from stash list.

**Time Travel**
When you made a mistake and you want to revert back to your previous commits you do time travel.

- `git reset HASH --soft` - soft reset is the least destructive. It will only change the commit that your HEAD is pointing. It preservs git Staging Area and your Working Directory.

- `git reset HASH --mixed` - it's a default reset so you don't have to use `--mixed` flag. All changes will be made inside our Working Directory. Staging Area will be empty.

- `git reset HASH --hard` - all the changes will be wipe out. Our working directory will be clean.

- `git reflog` - use when you want to display every action that was made inside your repository. It's often used along with reset. **When you experimented with resets and made a mistake, this command will help you.**

## Remote Workflow

- `git fetch` - this command fetches changes that were made inside remote repository to your local repository.

- `git pull` - fetches changes and merges them at the same time.

- `git push` - pushes changes made inside your local repository to remote repository. Good practice is to pull changes before you push. It only updates your **current branch.**

**Information about remote repos**

- `git remote -v` - displays information about your remote repositories. 

- `git remote set-url orgin NEWURL` - use this if you changed your remote repository name or you want your local repository to point to another remote repository.

- `git remote show origin` - displays detailed information about remote repository.


**Local branches workflow**

- `git push -u orgin BRANCHNAME` - use this command when you want to add branch to your remote repository.

- `git fetch -p` - looks for dead branches and removes references to them. It's helpful if you deleted branches from Github website.

- `git fetch` - use this when you want to update local branches list. It's useful when you create branch directly from Github website.

- `git pull --all` - this command will update all branches from your remote repo.

- `git push origin :BRANCHNAME` - it will delete branch from your remote repository

**Changing default branch**

It's usually the good idea to have one **stable** branch that is production ready and one **development branch** where you work on your code. When your development branch will reach production ready state then you merge those changes to the stable branch.
:exclamation: Be careful which default branch you choose, because it **affetcs cloning and merging options.**




**Rebase**

- `git pull --rebase` - if you have one commit made in your local repository and one commit made remotely. You do pull after your local commit. Then order of your local commits will be **local -> remote.** When you add `--rebase` flag this order will be reversed **remote -> local.**

## Tags

**Creating aliases**

- `git config --global alias.ALIASNAME "COMMAND "` - this is pretty useful if we regularly use more complicated commands and we want to have an alternative and simpler way to do it.

