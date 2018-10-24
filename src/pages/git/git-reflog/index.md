---
title: Git Reflog
---
## Git Reflog

This command's syntax is as follows:
```bash
git reflog <subcommand> <options>
```

The reference log or "reflog" in short is considered as a safety mechanism by many git users. It keeps track of the tips of branches and other references when they were updated in the local repository.

By executing `git reflog`, you would get an output similar to what is displayed below.

    011f38c HEAD@{0}: merge upstream/master: Fast-forward
    952f00b HEAD@{1}: reset: moving to 952f00b390efd2b2c03921a01defeaaac370c328
    195cd73 HEAD@{2}: rebase: aborting
    011f38c HEAD@{3}: pull upstream master --rebase: checkout 011f38c99eedb9d28657fcb73e925ad4b32ab8e6
    195cd73 HEAD@{4}: reset: moving to HEAD@{1}
    a6e6bec HEAD@{5}: commit (merge): Merge remote-tracking branch 'upstream/master'
    195cd73 HEAD@{6}: cherry-pick: add a section on git show
    952f00b HEAD@{7}: checkout: moving from clone to master
    0702c3e HEAD@{8}: checkout: moving from master to clone
    952f00b HEAD@{9}: reset: moving to 952f00b390efd2b2c03921a01deffaaac370c328
    bf9e3cb HEAD@{10}: merge upstream/master: Merge made by the 'recursive' strategy.
    
`HEAD@{0}` means where you presently at in your current branch. For example `HEAD@{5}` means where the `HEAD` used to be in 5 moves before.

Yuu can use `git show` command to see the "log" of the reference you would provided. As the reference for `git show` command, you could use either the position of head `HEAD` or the hash associated with it. Therefore both of the following commands would provide the same output.

```bash
git show HEAD@{2}
```
or
```bash
git show 195cd73
```

You can use references you'd get from `git reflog` in association with command like `reset`, `cherry-pick`, `checkout` and `merge`. But the most common use case would be to use it with `git reset` which would use to reset back to a certain point of git history. That's why the `git reflog` is considered as a safety net.


### More Information:
- [Git documentation - git reflog](https://git-scm.com/docs/git-reflog)

