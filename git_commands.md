# Git Commands

### Setup and Config

**`git config --global user.name "Your Name"`** - sets user name for all projects (--global)

**`git config --global user.email "john@example.com"`** - sets user e-mail address for all projects

**`git config --global color.ui auto`** - gets coloured diff output

**`git config --list`** - shows your current settings

### Getting and Creating Projects

**`git init`** - initiates a new git repository in current working directory;
				(creates new hidden directory `.git`)
                
**`git clone <address of repo>`** - clones a repository into the current directory

### Basic Snapshotting

**`git status`** - prints the status of git repository (from current directory)

**`git add [file]`** - adds file to staging area

**`git commit`** - records changes to the repository

**`git commit --amend`** - changes message of last commit (never amend commits that have been pushed to a public repository!)

**`git reset [--] <paths>`** - removes file(s) from staging area

**`git reset --soft HEAD~1`** - cancels last commit, preserving local changes

**`git reset --hard HEAD~1`** - cancels last commit, without preserving local changes

**`git reset origin/master`** - cancels non-pushed commits

### Inspection and Comparison

**`git log`** - shows a list of recent commits

**`git log -n [#]`** - shows a list of # recent commits

**`git log --graph --oneline [branch 1] [branch 2]`** - prints log for both chosen branches

**`git diff [ID ID]`** - compares two versions of the code followed by commits IDs

**`git diff`** - with no IDs, compares version of files between working directory and staging area

**`git diff --staged`** - compares version of files between staging area and repository

**`git show [SHA-ID]`** - shows the introduced changes in commit (followed by ID) in comparision to parent commit

### Branching and Merging
#### Checkout

**`git checkout <SHA-ID>`** - puts you into a "detached head" state, which basically just means that the current sha that your working copy has checked out, doesn't have a branch pointing at it. In other words, it takes you to the state of your project in a particular point in history (markde by sha-id).

If you haven't made any commits yet, you can leave detached head state by simply checking out whichever branch you were on before checking out the commit sha:

**`git checkout <branch>`** - switches from one branch to another

**`git checkout -b <new_branch_name>`** - simultaneously creates new branch and set "HEAD" to work on it

#### Branch

**`git branch`** - shows local branches

**`git branch -a`** - shows all branches and points out current branch
  
**`git branch -d <branch_name>`** - deletes chosen branch (usually after merging)

**`git show-branch -a`** - shows both remote-tracking branches and local branches and prints their most recent commit message

#### Merge

**`git merge [branch_1] [branch_2]`** - merges branch_1 into branch_2

### Sharing and Updating Projects

**`git remote`** - lists remote repositories

**`git remote add <remote_name> <remote_address>`** - adds new repo named <remote_name> at <remote_address> address (i.e. http, ssh)

**`git push [remote_name] [branch_name]`** - pushes branch [branch_name] to the [remote_name] repo   

**`git pull [remote_name] [branch_name]`** - fetches the branch [branch_name] and merge it with local branch

**`git fetch [remote_name]`** - fetching the remote repo without merging with local master branch

---

### Command batches
###### Removing untracked files from repository
```
git rm -r --cached .
git add .
git commit
```

