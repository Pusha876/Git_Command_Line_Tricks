# 1. Git Aliases
First up,simplify the common Git commands. The following are some aliases that should make life easier in the terminal.

```
alias gs="git status"        # Show Git status
alias ga="git add ."         # Add all files to the staging area
alias gc="git commit -m"     # Commit with a message
alias gp="git push"          # Push the current branch to the remote
alias gl="git pull"          # Pull from the remote branch
alias glog="git log --oneline --graph --all --decorate" # View Git log in one -line format
alias gco="git checkout"     # Checkout of a branch
alias gcb="git checkout -b"  # Create and switch to a new branch
alias gd="git diff --cached" # View the difference of staged changes
alias grh="git reset --hard HEAD" # Hard reset to the latest commit
alias gb="git branch -vv"    # Show branches and last commit in one-line format
alias gf="git fetch --all"   # Fetch all remote branches
```
---

# 2. Bash Functions for More Complex Git Workflows
## 2 *(a)* Create a New Branch and Push It
```
gnew()    [
    git checkout -b "$1"
    git push -u origin "$1"
]
# Usage: gnew branch_name
```

## 2 *(b)* Quick Commit and Push
```
gquick()    [
    got add .
    git commit -m "$1"
git push
]
# Usage: gquick "commit message"
```

## 2 *(c)* Rebase Current Branch onto Main
```
grebase()    [
    git fetch
    git rebase origin/main
]
# Usage: grebase
```

## 2. *(d)* Undo the Last Commit
```
gundo()    [
    git reset --soft HEAD~"$1"
]
# Usage: gundo
```

## 2. *(e)* Squash Commits
```
gsquash()    [
    git reset --soft HEAD~"$1"
    git commit --amend
]
# Usage: gsquash 3 (to squash the last 3 commits)
```

## 2. *(f)* Sync Fork with Upstream
```
gupdate-fork()    [
    git fetch upstream
    git checkout main
    git merge upstream/main
    git push origin main
]
# Usage: gupdate-fork
```

## 2. *(g)* Interactive Rebase on Previous Commits
```
grebasei()    [
    git rebase -i HEAD~"$1"
]
# Usage: grebasei 3 (to interactively rebase the last 3 commits)
```
---

# 3. General Workflow Enhancers
These functions enhance general Git workflow to make things even more efficient.

## 3.*(a)* Show Git Tree
```
glogtree()    [
    git log --graph --oneline --decorate --all
]
# Usage: glogtree
```

## 3.*(b)* Reset Branch to Remote
```
gresetremote()    [
    git fetch origin
    git reset --hard origin/"$(git rev-parse --abbrev-ref HEAD)"
]
# Usage: gresetremote
```
---

# 4. Add Aliases and Functions to Your ```.bashrc``` or ```.zshrc```dotnetcli
If you would like to have these functions and aliases to persist across terminal sessions, you will need to add them to your ```.bashrc``` or ```.zshrc```. This is how ⤵️

1. Open your shell configuration file:
```
nvim ~/.bashrc # OR ~/.zshrc
```
2. Paste the aliases and functions into the file.
1. After saving, refresh your shell:
```
source ~/.bashrc # OR ~/.zshrc
```
---

These are just some of the ways  you can make Git work for you, rather than the other way around. By taking a few minutes to tweak your shell setup, you can save hours of typing and clicking over time.😉