
# Guide to Squashing Commits

Squashing commits is a technique used to combine multiple commits into one. This is especially helpful when you want to clean up your commit history before merging a feature branch into the main branch. This guide will walk you through how to squash commits in Git.

## 1. Use Case for Squashing Commits
Squashing is typically done in the following situations:
- Cleaning up a messy commit history before merging to the main branch.
- Combining minor fixes or typos into a single commit for a more meaningful history.
- Keeping a clear, readable commit history for easier debugging.

## 2. Steps to Squash Commits

### 2.1. Check Your Commit History
Before squashing, you might want to review your commit history. Use the following command to view the last few commits:
```bash
git log --oneline
```
This will give you a list of commits with their hashes and short descriptions.

### 2.2. Start an Interactive Rebase
To squash commits, you need to perform an interactive rebase. Specify how many commits you want to rebase (e.g., the last 3 commits):
```bash
git rebase -i HEAD~3
```
This command opens a text editor with a list of the last 3 commits. The list will look something like this:
```
pick 1234abc Commit message 1
pick 5678def Commit message 2
pick 9abc123 Commit message 3
```

### 2.3. Mark Commits to Be Squashed
In the text editor, change the word `pick` to `squash` (or `s` for short) for all commits you want to squash into the first one. For example, to squash the last two commits into the first one, update the list like this:
```
pick 1234abc Commit message 1
squash 5678def Commit message 2
squash 9abc123 Commit message 3
```

### 2.4. Save and Close the Editor
Once you've made your changes, save and close the editor. Git will begin the rebase process and combine the commits into one.

### 2.5. Edit the Commit Message (Optional)
After squashing, Git will open the editor again, allowing you to edit the commit message. You can either keep all commit messages, write a new one, or remove unnecessary lines. After editing, save and close the editor.

### 2.6. Complete the Rebase
If there are no conflicts, the rebase will complete, and you will have successfully squashed the commits into a single one.

### 2.7. Push the Changes
If the commits you squashed were already pushed to a remote branch, you'll need to force-push the changes:
```bash
git push --force
```
**Note:** Force-pushing should be done with caution, as it rewrites history and can affect other collaborators.

## 3. Handling Merge Conflicts During Rebase
If there are merge conflicts during the rebase, Git will stop and allow you to resolve the conflicts. You can use the following steps:
1. Resolve the conflicts in the affected files.
2. Stage the resolved files:
   ```bash
   git add <file>
   ```
3. Continue the rebase:
   ```bash
   git rebase --continue
   ```
Repeat this process until all conflicts are resolved and the rebase is complete.

## 4. Example Workflow

Here’s a practical example of how you might squash your commits:

1. View your last 5 commits:
   ```bash
   git log --oneline
   ```
2. Start an interactive rebase for the last 5 commits:
   ```bash
   git rebase -i HEAD~5
   ```
3. Change `pick` to `squash` for the commits you want to combine.
4. Save and close the editor.
5. Edit the commit message if necessary.
6. Force-push to the remote repository:
   ```bash
   git push --force
   ```

## 5. Best Practices
- **Do not squash commits on public branches**: If others are working on the same branch, squashing commits can cause issues with history rewriting.
- **Squash before merging**: It’s a good idea to squash commits before merging to the main branch to keep the history clean.
- **Use clear commit messages**: After squashing, make sure the resulting commit message is clear and descriptive of what the squashed commits represent.

## 6. Conclusion
Squashing commits is a useful technique for maintaining a clean and readable commit history. By following these steps, you can squash multiple commits into a single one, ensuring that your repository’s history is concise and easy to follow.
