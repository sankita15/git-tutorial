## Git Branching - Rebasing

* Rebasing: you can take all the changes that were committed on one branch and replay them on a different branch.

Suppose the scenario is as below:
![](../images/basic-rebase-1.png)

Now you want to integrate your changes to master branch, you can perform a 3-way merge also and end up having a merge commit to perform the task.
Other way of doing it as **you can take the patch of the change that was introduced in C4 and reapply it on top of C3.**
This is rebasing.

In short taking branch diffs and applying it on top of the other branch from which you want to rebase.

```text
$ git checkout experiment
$ git rebase master
First, rewinding head to replay your work on top of it...
Applying: added staged command
```

![](../images/basic-rebase-3.png)

the end product from 3-way merge i.e., the merge commit and from rebase will be same just rebase provides a cleaner history.

```text
$ git checkout master
$ git merge experiment
```

Once you are done with rebase, you need to merge the changes from master also so that git will perform a fast forward merge results in cleaner history.

Notes: git rebase takes the diff of C4 commit and started applying on top of C3 commit if while applying any conflicts came git will ask you to resolve otherwise it will apply smoothly.
Now your experiment branch is at C4' commit(not C4) which is having all the synced changes with master, but master is still at C3 so you need to go to master and merge the experiment branch(as it is having the updated changes) then master and experiment will be in sync(at C4') and you can delete experiment safely.