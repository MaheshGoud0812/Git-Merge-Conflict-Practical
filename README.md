# Git Merge Conflict Practical

## Aim
To understand how a merge conflict occurs when two Git branches modify the same line, and how to resolve it.

## Files and branches
- `main`: contains the main branch change.
- `feature`: contains a different change to the same line.
- `file.txt`: the file used for the demonstration.

## Steps performed
1. Created `file.txt` on `main`.
2. Created a branch named `feature`.
3. Changed the same line differently on both branches:
   - On `main`: `Main branch update.`
   - On `feature`: `Feature branch update.`
4. Opened pull request #1 from `feature` to `main`.
5. GitHub reported that the branches had merge conflicts because both changed the same line.
6. Resolved the conflict by keeping both updates in the final file on `main`.

## How a conflict looks
When Git cannot automatically combine the changes, conflict markers can look like this:

```text
<<<<<<< HEAD
Main branch update.
=======
Feature branch update.
>>>>>>> feature
```

Remove the markers and edit the file to the desired final content.

## Final resolved content
```text
Welcome to Git
Initial content
Main branch update.
Feature branch update.
```

## Useful local Git commands
```bash
git checkout main
git merge feature
# If a conflict occurs, open the conflicted file and resolve the markers.
git add file.txt
git commit -m "Resolve merge conflict"
```

## Result
A merge conflict was successfully demonstrated. Both branches modified the same line, GitHub identified the conflict in pull request #1, and the final version preserves both changes.

**Note:** Pull request #1 was closed without merging; the resolved content was committed directly to `main`.
