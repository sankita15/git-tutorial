## Git Branching - Remote Branches

#### Pushing
```text
$ git push remote <branch>
Counting objects: 24, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (15/15), done.
Writing objects: 100% (24/24), 1.91 KiB | 0 bytes/s, done.
Total 24 (delta 2), reused 0 (delta 0)
To https://github.com/schacon/simplegit
 * [new branch]      serverfix -> serverfix
```

If you are pushing abranch along with your commit and you dont want the same name of the branch in the remote you can rename the branch specifically in remote by using this command:
```text
git push origin <branch_old_name>:<branch_new_name>
```

Now if you want to work with someone on thier branch and you fetch thier branch:
```text
$ git fetch origin
remote: Counting objects: 7, done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 3 (delta 0)
Unpacking objects: 100% (3/3), done.
From https://github.com/schacon/simplegit
 * [new branch]      serverfix    -> origin/serverfix
```

fetch will just bring down new-remote-tracking branches, but you will not have a local editable copies.
You will not have a new branch, you will just have a branch pointer that you can't modify.

If you want to work and do editing in the branch then after fetch you need to merge that branch to your current working branch.
```text
git merge origin/<branch>.
```

origin/<branch> is the only pointer that is available after fetch that you can't edit. 

**Notes: If you want to create a new branch having base with that pointer.**

```text
$ git checkout -b serverfix origin/serverfix
Branch serverfix set up to track remote branch serverfix from origin.
Switched to a new branch 'serverfix'
```

**This gives you a local branch that you can work on that starts where origin/serverfix is.Your remote serverfix will not be changed as it a new local branch you have created.**
Here serverfix is a tracking branch.
Checking out a local branch from a remote-tracking branch automatically creates what is called a “tracking branch” (and the branch it tracks is called an “upstream branch”).


#### Pulling
```text
git fetch + git merge = git pull
```

git pull will look up all the changes and remote and tracking branches in the server, fetches it and then immediately merges it in the remote branch.


#### Deleting Remote Branches

```text
$ git push origin --delete serverfix
To https://github.com/schacon/simplegit
 - [deleted]         serverfix
```

Basically all this does is remove the pointer from the server.The Git server will generally keep the data there for a while until a garbage collection runs, so if it was accidentally deleted, it’s often easy to recover.