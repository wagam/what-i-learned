# Git

### My git aliases

```text
git lga  = git log --decorate --oneline --graph --all
git co = git checkout
git st = git status
gfa = git fetch --all --prune
gup = git pull --rebase
```

### What I understand about git :

A commit points to its parent by storing the parent commit number \(sha1\). 

Every commit is a summary of all changes from the last save.

### Git tips:

Before a pull-request, do a git rebase origin/&lt;branch-to-merge&gt;. It avoid merge conflicts after review.

Do small commits, you can revert easier.

If you want to add something to your previous commit \(small fix\) you can do 

```text
git commit --all --amend
```

If you want to reuse some commit from another branch, do 

```text
git cherry-pick <commit-sha1>
```

If you have a lot of small commits and you want to manage them differently, e.g. a feature commit, you can do an interactive rebase with 

```text
git rebase -i <branch-to-rebase>
```



