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

If you want to keep your updates of some files but you don't want to commit them, you can use 

```text
git stash <file-path> -m "your-stah-message-to-remember-it"
```

If you want to know where two commits started to diverge you can use

```text
git bisect <commit1> <commit2>
```

See [https://git-scm.com/docs/git-bisect](https://git-scm.com/docs/git-bisect) for more info about git bisect

### Git workflows

Classic git workflow

![](https://miro.medium.com/max/577/1*AAU1VCV8LMHvVPBYxMBsxg.png)

