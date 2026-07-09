# Git Commands
## Setup Git - Configuring user information used across all local repositories
### To check if git is properly installed
```bash
git --version
```
### set a name ( Usually github profile name ) that is identifiable for credit when review version history
```bash
git config --global user.name "[firstname lastname]"
git config --global user.name "GauravKaushik1"
```
### set a valid email address(your github linked email) that will be associated with each history marker
git config --global user.email "[valid-email@gmail.com]"
git config --global user.email "gauravkaushik1999gko@gmail.com
### see global config
git config --global --list
## Setup and INIT - Configuring user information, initializing and cloning repositories
### initialize an existing directory as a Git repository
git init
#### add a git url to origin
git remote add origin [url]
### retrieve an entire repository from a hosted location via URL
git clone [url]
## git bash commands list directory
### list files (except hidden files)
ls
### list all files including hidden files
ls -a
## STAGE & SNAPSHOT - Working with snapshots and the Git staging area
### show modified files in working directory, staged for your next commit
git status
### add a file as it looks now to your next commit (stage)
git add [file]
### add all files as it all looks now to your next commit (stage)
git add .
### unstage a file while retaining the changes in working directory
git reset [file]
### unstage all files while retaining the changes in working directory
git reset
### diff of what is changed but not staged
git diff
### diff of what is staged but not yet committed
git diff --staged
### commit your staged content as a new commit snapshot
git commit -m "[some message]"
## BRANCH & MERGE-Isolating work in branches, changing context, and integrating changes
### list your branches. a * will appear next to the currently active branch
git branch
### rename branch
git branch -M [branch-new-name]
git branch -M feature1
#### rename branch as main (in legacy git installation branch name used to be master but now it is not prevalent so git branch main is to be used everywhere)
git branch -M main
### create a new branch at the current commit
git branch [new-branch-name]
#### create a new branch and switch to it
git checkout -b [new-branch-name]
### switch to another branch and check it out into your working directory
git checkout [branch-name]
### delete specific branch
git branch -d [branch-name]
### merge the specified branch’s history into the current one
git merge [branch]
## INSPECT & COMPARE-Examining logs, diffs and object information
### show all commits in the currently active branch’s history
git log
### show the commits on branchA that are not on branchB
git log branchB..branchA
### show the diff of what is in branchA that is not in branchB
git diff branchB...branchA
### show the commits that changed file, even across renames
git log --follow [file]
### show any object in Git in human-readable format
git show [SHA]
## TRACKING PATH CHANGES - Versioning file removes and path changes
### delete the file from project and stage the removal for commit
git rm [file]
### change an existing file path and stage the move
git mv [existing-path] [new-path]
### show all commit logs with indication of any paths that moved
git log --stat -M
## IGNORING PATTERNS - Preventing unintentional staging or commiting of files
logs/
*.notes
pattern*/
### Save a file with desired patterns as .gitignore with either direct string matches or wildcard globs.
### system wide ignore pattern for all local repositories
git config --global core.excludesfile [file]
## SHARE & UPDATE-Retrieving updates from another repository and updating local repos
### add a git URL as an alias
git remote add [alias] [url]
git remote add origin [url]
### fetch down all the branches from that Git remote
git fetch [alias]
### merge a remote branch into your current branch to bring it up to date
git merge [alias]/[branch]
### Transmit local branch commits to the remote repository branch
git push [alias] [branch]
#### using git push alone-setting up default push branch
git push -u origin [branch-name]
git push -u origin main
git push
### fetch and merge any commits from the tracking remote branch
git pull
## REWRITE HISTORY-Rewriting branches, updating commits and clearing history
### apply any commits of current branch ahead of specified one
git rebase [branch]
### clear staging area, rewrite working tree from specified commit
git reset --hard [commit]
## TEMPORARY COMMITS-Temporarily store modified, tracked files in order to change branches
### Save modified and staged changes
git stash
### list stack-order of stashed file changes
git stash list
### write working from top of stash stack
git stash pop
### discard the changes from top of stash stack
git stash drop
