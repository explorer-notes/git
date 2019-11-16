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

- `git checkout -- FILENAME` - this command will be useful if you want to remove changes from Staging Area as well as your local repository. 
