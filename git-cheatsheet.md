# Git Cheat Sheet

A practical Git cheat sheet for everyday development, GitHub workflows, and fixing the usual “what have I done?” situations.

---

## Setup

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --list
```

Use these commands to set your identity and inspect your current Git configuration.

---

## Starting a Repository

```bash
git init
```

Initialize a new Git repository in the current folder.

```bash
git clone <url>
```

Clone an existing repository from GitHub or another remote source.

---

## Daily Basics

```bash
git status
```

Check what changed, what is staged, and what branch you are on.

```bash
git add <file>
git add .
```

Stage one file or all changed files.

```bash
git commit -m "Describe your change"
```

Commit staged changes with a message.

```bash
git commit --amend
```

Edit the last commit or add newly staged changes to it.

---

## Branching

```bash
git branch
```

List local branches.

```bash
git branch <name>
```

Create a new branch.

```bash
git switch <name>
```

Switch to an existing branch.

```bash
git switch -c <name>
```

Create and switch to a new branch.

```bash
git merge <branch>
```

Merge another branch into the current branch.

```bash
git rebase <branch>
```

Replay your commits on top of another branch.

```bash
git branch -d <name>
```

Delete a local branch after it has been merged.

```bash
git branch -D <name>
```

Force-delete a local branch.

---

## Remotes and GitHub

```bash
git remote -v
```

Show connected remotes.

```bash
git remote add origin <url>
```

Connect your local repository to a remote repository.

```bash
git remote set-url origin <url>
```

Change the remote URL.

```bash
git push -u origin <branch>
```

Push a branch and set the upstream tracking branch.

```bash
git push
```

Push committed changes to the tracked remote branch.

```bash
git fetch
```

Download remote changes without merging them.

```bash
git pull
```

Fetch and merge remote changes.

```bash
git pull --rebase
```

Fetch remote changes and replay your local commits on top.

```bash
git push --force-with-lease
```

Safely force-push after rewriting history.

> Prefer `--force-with-lease` over `--force`. It is less likely to overwrite someone else’s work, which is nice if you enjoy having teammates.

---

## Undoing Changes

```bash
git restore <file>
```

Discard unstaged changes in a file.

```bash
git restore --staged <file>
```

Unstage a file without deleting the changes.

```bash
git revert <commit>
```

Create a new commit that undoes another commit.

```bash
git reset --soft HEAD~1
```

Undo the last commit but keep changes staged.

```bash
git reset --mixed HEAD~1
```

Undo the last commit and keep changes unstaged.

```bash
git reset --hard HEAD~1
```

Undo the last commit and delete the changes.

> Warning: `reset --hard` discards work. Use it carefully unless your goal is emotional damage.

---

## Inspecting History

```bash
git log --oneline
```

Show a compact commit history.

```bash
git log --oneline --graph --decorate --all
```

Show a visual branch history.

```bash
git diff
```

Show unstaged changes.

```bash
git diff --staged
```

Show staged changes.

```bash
git blame <file>
```

Show who last changed each line of a file.

```bash
git show <commit>
```

Show details of a specific commit.

---

## Stashing Work

```bash
git stash
```

Temporarily save uncommitted changes.

```bash
git stash push -m "message"
```

Stash changes with a description.

```bash
git stash list
```

List saved stashes.

```bash
git stash pop
```

Apply the latest stash and remove it from the stash list.

```bash
git stash apply
```

Apply the latest stash but keep it in the stash list.

```bash
git stash drop
```

Delete the latest stash.

---

## Handling Merge Conflicts

When Git reports a conflict:

```bash
git status
```

See which files have conflicts.

Open each conflicted file and look for markers like:

```text
<<<<<<< HEAD
your changes
=======
incoming changes
>>>>>>> branch-name
```

Edit the file to keep the correct version, then run:

```bash
git add <file>
git commit
```

If you are rebasing, continue with:

```bash
git rebase --continue
```

To cancel a rebase:

```bash
git rebase --abort
```

---

## Tags

```bash
git tag
```

List tags.

```bash
git tag v1.0.0
```

Create a lightweight tag.

```bash
git tag -a v1.0.0 -m "Release v1.0.0"
```

Create an annotated tag.

```bash
git push origin v1.0.0
```

Push a tag to the remote.

---

## Useful Aliases

```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.cm commit
git config --global alias.lg "log --oneline --graph --decorate --all"
```

After setting these, you can use commands like:

```bash
git st
git lg
```

---

## Common Workflows

### Create a new feature branch

```bash
git switch main
git pull
git switch -c feature/my-feature
```

### Save and push your work

```bash
git add .
git commit -m "Add my feature"
git push -u origin feature/my-feature
```

### Update your branch with latest main

```bash
git switch main
git pull
git switch feature/my-feature
git rebase main
```

### Undo the last commit but keep your work

```bash
git reset --soft HEAD~1
```

### Throw away local changes in one file

```bash
git restore <file>
```

---

## Dangerous Commands

These commands can delete work or rewrite history:

```bash
git reset --hard
git clean -fd
git push --force
git rebase
```

Use them only when you understand the result. Git is powerful, but so is a chainsaw, and nobody stores wedding photos in a chainsaw.
