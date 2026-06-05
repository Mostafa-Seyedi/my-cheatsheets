# Git Cheat Sheet

## Setup
- `git config --global user.name "Name"` — set username
- `git config --global user.email "email"` — set email
- `git config --list` — view all config

## Basics
- `git init` — initialize a repo
- `git clone <url>` — clone a repo
- `git status` — check current state
- `git add <file>` — stage a file
- `git add .` — stage all changes
- `git commit -m "msg"` — commit with message
- `git remote -v` — See your connected GitHub remote
- `git commit --amend` — amend last commit

## Branching
- `git branch` — list branches
- `git branch <name>` — create branch
- `git checkout -b <name>` — create & switch branch
- `git switch <name>` — switch branch (modern)
- `git merge <branch>` — merge into current
- `git rebase <branch>` — rebase onto branch
- `git branch -d <name>` — delete branch

## Remote
- `git remote add origin <url>` — add remote
- `git push origin <branch>` — push branch
- `git pull` — fetch + merge
- `git fetch` — fetch only
- `git push --force-with-lease` — safe force push

## Undoing
- `git restore <file>` — discard unstaged changes
- `git restore --staged <file>` — unstage a file
- `git revert <commit>` — revert a commit
- `git reset --soft HEAD~1` — undo last commit, keep changes staged
- `git reset --hard HEAD~1` — undo last commit, discard changes

## Inspection
- `git log --oneline` — compact log
- `git log --graph --all` — visual branch graph
- `git diff` — unstaged changes
- `git diff --staged` — staged changes
- `git blame <file>` — who changed what line
- `git stash` — stash changes
- `git stash pop` — apply stash 
