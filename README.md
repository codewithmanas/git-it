# Basic Git Commands
## Step 1 (Initialize Repository)

run the command below to initialize the repository. After initializing the repo a hidden .git directory will be created.
`git init`

### Un-initialize Repository Completely

run the command below to un-initialize the repository. After un-initializing the repo a all files will be removed.
`rm -rf .git` 

### To Create .gitignore file

`touch .gitignore`

### Remove .gitignore file

`rm .gitignore`

## To Know Status Of The Repo

`git status`

## Step 2 (To stage the file to include in what will be committed)

`git add <FileName>`  (For Single File)

`git add .`  (For All Files)

### To unstage the file

`git rm --cached <FileName>`  (For Single File)

`git restore --staged <FileName>`  (For Single File)

`git reset HEAD -- .`  (For All Files)

`git reset .`  (For All Files)

### To unstage the files and delete them forever

`git reset --hard`

## Step 3 (To Commit the file)

`git commit -m "msg here"`

### To know all the branches in your current codebase 
run the command below

`git branch`

## Step 4 (To switch between the branches )
`git checkout -b feature`  ( -b is for creating a branch named feature if not available)

`git checkout <BranchName>`  (If branch is already present.)

### to switch branch and save the changes without commiting them
`git stash -u`

`git stash pop`  (first revert back to same branch and  commit changes)

## Step 5 (To merge to master)
`git merge <NewBranchName>`  (first go to master branch)

## Step 6 (To connect local repo to remote repo)
`git remote add origin <git repo url>`  

## Step 7 (To push to remote github repo)
`git push -u origin master`

## Step 8 (To clone remote repo to local system) (copy from remote repo to local system)
`git clone <git repo url>` (first, fork the repo if this is repo of another user)


# Trouble-shooting :-

## Default behavior of `git push` without a branch specified

### To view the current configuration:
#### `git config push.default`

### To set a new configuration: (You can set up default behavior for your git with push.default)
#### `git config push.default current`

### If you have many repositories and want the same for all then
#### `git config --global push.default current`

>The **current** in this setup means that by default you will **only push the current branch** when you do **git push**

Other options are:

-   `nothing`: do not push anything
-   `matching`: (default before Git 2.0) push all matching branches .\ All branches having the same name in both ends are considered to be matching.
-   `upstream`: push the current branch to its upstream branch (`tracking` is a deprecated synonym for upstream)
-   `current`: push the current branch to a branch of the same name
    
-   `simple`: (new in Git 1.7.11, default since Git 2.0) like upstream, but refuses to push if the upstream branch's name is different from the local one

	This is the safest option and is well-suited for beginners.


> The simple, current and upstream modes are for those who want to push out a single branch after finishing work, even when the other branches are not yet ready to be pushed out

### After doing above things, we can run `git push` normally.

