# 1. Set Global Configuration
 Ensure your commits are tagged with the correct identity.

```
git config --global user.name "Your Name"
git config --global user.email"your@example.com"
```

💡**Tip:** Use ```--local``` instead of ```--global``` to set project-specific configurations.

# 2. Undo the Last Commit (without losing changes)
If you made a mistake in the last commit, you can undo it.
```
git reset --soft HEAD~1
```
This leaves your changes staged, so you can amend the commit or fix the issue.

# 3. Amend the Last Commit
Forgot to include a change or want update the commit message?
```
git add .
git commit --amend -m "Updated commit message"
```
This updates the previous commit without creating a new one.

# 4. Stash Uncommitted Changes
Need to quickly switch branches without committing?
```
git stash
```
💡 Retrieve the stash later with:
```
git stash pop
```

# 5. View Commit History Graphically
Visualizing the commit history marked it easier to understand the project's state.
```
git log --graph --oneline --all
```

# 6. Change the Commit Author
Change the author of the last commit.
```
git commit --amend --author="New Author <newauthor@example.com>"
```
# 7. Check Differences in Staged Changes
Use git diff to compare files at different stages.
```
git diff --staged
```
This shows the changes that are staged but not yet committed.

# 8. Find a Bug with Bisect
Use git bisect to find the commit that introduces a bug.
```
git bisect start
git bisect bad # Current commit is bad
git bisect good <commit-hash> # A known commit
```
Git will walk through the commit history to identify the problematic commit.

# 9. Rebase for a Clean Commit History
Rebasing rewrites your commit history for clarity.
```
git rebase -i HEAD~3
```
Thais lets you edit, squash, or reorder your last 3 commits.

# 10. Cherry-Pick Specific Commits
Want to bring a specific commit from another branch?
```
git cherry-pick <commit-hash>
```

# 11. List All Branches (Local and Remote)
See which branches are available.
```
git branch -a
```

# 12. Clean Untracked Files and Directories
Quickly remove unwanted files that  are not tracked by Git.
```
git clean -fd
```
💡Use ```-n``` for a dry run to preview what will be removed.

# 13. Track an Upstream Branch
Keep your local branch in sync with a remote branch.
```
git branch --set-upstream-to=origin/main
```

# 14. Squash Commits with Interactive Rebase
Combine multiple commits into one.
```
git rebase -i HEAD~n # Replace 'n' with the number of commits
```
# 15. View the File at a Specific Commit
Check a file's state at a particular commit.
```
git show <commit-hash>:path/to/file
```

# 16. Edit the .gitignore After Committing
If you forgot to ignore certain files, update .gitignore.
```
echo "node_modules/">> .gitignore
git rm -r --cached node_modules/
git commit -m *Update .gitignore"
```

# 17. Revert a Pushed Commit
Undo changes from a specific commit without changing history.
```
git revert <commit-hash>
```

# 18. Fetch Only Metadata
Want to avoid fetching the whole repository?
```
git fetch --dry-run
```
This lets you see what would be fetched without actually downloading data.

# 19. Blame a Line of Code
Find out who wrote a specific line in a file.
```
git blame path/to/file
```

# 20 Reset a File to the Last Commit
Discard local changes to a specific file.
```
git checkout --path/to/file
```
These 20 Git command-line tricks can make your development process smoother, whether you are working alone or with a team.

Happy coding! 🚀
