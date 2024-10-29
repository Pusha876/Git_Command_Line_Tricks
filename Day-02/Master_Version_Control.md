# 1. Setting Up Your Git Repository
## Initialize a New Repository
```
git init
```
This command initializes a new Git repository in your project folder. Use it when starting a a new project or to begin tracking an existing one.

## Clone an Existing Repository
```
git clone <repository-url>
```
Clone an existing repository from a remote source like GitHub or Bitbucket. This is useful for contributing to a project or using an open-source library.

# 2. Configuring Git
## Set Your Username

git config <span style="color: red;"> --global.</span>
 user.name <span style="color: yellow;"> "Your Name" </span>

Sets your username for all Git repositories on your system.

## Set Your Email

<span style="color: red;"> 1 </span> user.email <span style="color: yellow;"> "your.email@examle.com" </span>

Set  your email address for commits.

## View Your Configuration

git config <span style="color: red;"> --list</span>

Lists all the Git configurations currently set.

---

# 3. Working with Your Repository
## Checking the Status of Your Repository
```
git status
```
Displays the state of your working directory and staging area, showing which changes have been staged, which haven't, and which files aren't being tracked by Git.

## Viewing a Log of Commits
```
git log
```
Shows a detail history of commits, including author, date, and commit message.

## Adding Changes to the Staging Area
```
git add <file-name>
```
Stages specific files for a commit. To stage all changes, use:

```
git add .
```

## Committing Changes

git commit <span style="color: red;"> -m </span> <span style="color: yellow;"> "Your commit message" </span>

Commits the staged changes with a descriptive message. It's good practice to write meaningful commit messages.

## Commit All Changes Directly

git commit <span style="color: red;"> -am </span> <span style="color: yellow;"> "Your commit message" </span>

Stages and commits all tracked files in one step. This command does not include untracked files.

## VViewing Changes
```
git diff
```
Shows the changes between your working directory and the staging area. Useful for reviewing what you've modified before committing.

## Viewing a Specific File's Changes
```
git diff <file-name>
```
Displays the changes made to a specific file.

## Removing Files
```
git rm <file-name>
```
Removing a file from your working directory and stages the deletion.

## Moving/Renaming Files
```
git mv <old-file-name> <new-file.name>
```
Moves or renames a file and stages the change.

---

# 4. Branching and Merging
## Create a New Branch
```
git branch <branch-name>
```
Creates a new branch. Branches are used to develop features or fixes in isolation from the master codebase.

## List all Branches
```
git branch
```
Lists all branches in your repository, highlighting the current branch.

## Switch to a Branch
```
git checkout <branch-name>
```
Switch to the specified branch.

## Create and switch to a New Branch
```
git checkout -b <branch-name>
```
Creates a new branch and immediately switches to it.

## Merge Branches
```
git merge <branch-name>
```
Merge changes from the specified branch into your current branch. This is typically used to integrate a feature branch into the main branch.

## Delete a Branch
```
git branch -d <branch-name>
```
Deletes a branch that has been merged. Use ```-D``` to force-delete a branch that hasn't been merged.

## Rebase Branches
```
git rebase <branch-name>
```
Rebases the current branch onto the specified branch. Rebasing can lead to a cleaner project history but should be used with caution, especially with shared branches.

---

# Working with Remotes
## Adding a remote Repository
```
git remote add origin <repository-url>
```
Connects your local repository to a remote server, typically a repository on GitHub, or Bitbucket.

## Viewing Remote Repositories
```
git remote -v
```
List all remotes and their URLs.

## Pushing Changes to Remote
```
git push origin <branch-name>
```
Pushes your commits to the remote repository. If it's your first push, you might need to set the upstream branch:
```
git push --set-upstream origin <branch-name>
```
Fetches and merges changes from the remote repository into your current branch.

## Fetching Changes from Remote
```
git fetch
```
Downloads objects and refs from another repository. Unlike ```git pull```, ```git fetch``` does not merge changes into your local branch automatically.

## Removing a Remote Repository
```
git remote remove <remote-name>
```
removes a remote from your repository.

# 6. Undoing Changes
## Unstage Changes
```
git reset <file-name>
```
Removes changes from the staging area but leaves them in your working directory.

## Discard Unstaged Changes
```
git checkout -- <file-name>
```
Reverts unstaged changes in your working directory to the last commit.

## Revert a Commit
```
git revert <commit-hash>
```
Creates new commit that undoes changes from a previous commit without altering the project history.

## Reset to a Previous Commit
```
git reset --hard <commit-hash>
```
Rolls back your project to a specific commit, discarding all changes made after that point. **Warning:** This is irreversible.

## Stash Changes
```
git stash
```
Temporarily saves changes that you don't want to commit yet, allowing you to work on something else.

## Apply Stashed Changes
```
git stash apply
```
Reapplies the most recently stashed changes to your working directory.

## Drop a Stash
```
git stash drop
```
Removes a specific stash from your list of saved changes.

# 7. Advanced Git Commands
## Cherry-Pick a Commit
```
git cherry-pick <commit-hash>
```
Applies the changes from a specific commit to your current branch.

## Squash Commits
```
git rebase -i HEAD~n
```
Combines multiple commits into one. Replace ```n``` with the number of commits you want to squash.

## View Commit History as a Graph
```
git log --graph --online --all
```
Displays the commit history in a graph format, showing branches and merges.

## Cleaning Up Untracked Files
```
git clean -f
```
Deletes untracked files from your working directory. Add ```-d``` to remove directories and ```-n``` to perform a dry run.
