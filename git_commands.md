# Git Commands

### Setup and Config

**`git config --global color.ui auto`** - gets coloured diff output

### Getting and Creating Projects

**`git init`** - initiates a new git repository in current working directory;
				(creates new hidden directory `.git`)
                
**`git clone <address of repo>`** - clones a repository

### Inspection and Comparison

**`git log`** - shows a list of recent commits

**`git log -n [#]`** - shows a list of # recent commits

**`git log --graph --oneline [branch 1] [branch 2]`** - prints log for both chosen branches

**`git diff [ID ID]`** - compares two versions of the code followed by commits IDs

**`git diff`** - with no IDs, compares version of files between
			working directory and staging area

**`git diff --staged`** - compares version of files between staging area and repository

**`git show [SHA-ID]`** - shows the introduced changes in commit (followed by ID) in comparision to parent commit

### Branching and Merging
#### Checkout

**`git checkout <SHA-ID>`** - puts you into a "detached head" state, which basically just means that the current sha that your working copy has checked out, doesn't have a branch pointing at it.

If you haven't made any commits yet, you can leave detached head state by simply checking out whichever branch you were on before checking out the commit sha:

**`git checkout <branch>`** - switches from one branch to another

**`git checkout -b <new_branch_name>`** - simultaneously creates new branch and set "HEAD" to work on it


**`git merge [branch_1] [branch_2]`** - merges branch_1 into branch_2

**`git branch`** - shows all branches and points out current branch
  
**`git branch -d <branch_name>`** - deletes chosen branch (usually after merging)

**`git show-branch -a`** - shows both remote-tracking branches and local branches.

---
<_segregation needed_> :wink:

**`git status`** - prints the status of git repository (from current directory)

**`git add [file]`** - adds file to staging area
 
**`git remote`** - lists remote repositories

**`git remote add <remote_name> <remote_address>`** - adds new repo named 
						[remote_name] at [remote_address] address (i.e. http, ssh)

**`git push [remote_name] [branch_name]`** - pushes branch [branch_name] to the [remote_name] repo   

**`git pull [remote_name] [branch_name]`** - fetches the branch [branch_name] and merge it with local branch

**`git fetch [remote_name]`** - fetching the remote repo without merging with local master branch

**`git commit`** - records changes to the repository

**`git reset [--] <paths>`** - removes file(s) from staging area

### Command batches
###### Removing untracked files from repository
```
git rm -r --cached .
git add .
git commit
```

