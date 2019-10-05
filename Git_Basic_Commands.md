## Git Basics - Working with Remotes

### Working with Remotes

##### Showing Your Remotes
```
git remote
```

This command lists the shortnames of each remote handle you’ve specified. By default origin is the default remote that git will have.

```
$ git remote -v
origin	https://github.com/schacon/ticgit (fetch)
origin	https://github.com/schacon/ticgit (push)
```

You can also specify -v, which shows you the URLs that Git has stored for the shortname to be used when reading and writing to that remote.

In case if you have more than one remote, the command list them all.

```
$ git remote -v
bakkdoor  https://github.com/bakkdoor/grit (fetch)
bakkdoor  https://github.com/bakkdoor/grit (push)
cho45     https://github.com/cho45/grit (fetch)
cho45     https://github.com/cho45/grit (push)
```

##### Adding Remote Repositories

To add a new remote Git repository as a shortname you can reference easily, run :
```
git remote add <shortname> <url>:
```

```
$ git remote add pb https://github.com/paulboone/ticgit
$ git remote -v
origin	https://github.com/schacon/ticgit (fetch)
origin	https://github.com/schacon/ticgit (push)
pb	https://github.com/paulboone/ticgit (fetch)
pb	https://github.com/paulboone/ticgit (push)
```

For example, if you want to fetch all the information that Paul has but that you don’t yet have in your repository:
```
$ git fetch pb
remote: Counting objects: 43, done.
remote: Compressing objects: 100% (36/36), done.
remote: Total 43 (delta 10), reused 31 (delta 5)
Unpacking objects: 100% (43/43), done.
From https://github.com/paulboone/ticgit
 * [new branch]      master     -> pb/master
 * [new branch]      ticgit     -> pb/ticgit
```

Paul’s master branch is now accessible locally as pb/master — you can merge it into one of your branches, or you can check out a local branch at that point if you want to inspect it.

##### Fetching and Pulling from Your Remote

git clone = this automatically adds remote repository under the name origin.
doing git fetch after git clone will fetch all the work in the remote repository but it will not merge the work that you currently have in your working directory so you need to do 2 operation git fetch and the git merge.
git Fetch + git Merge = git pull

##### Pushing to Your Remotes

When you have your project at a point that you want to share, you have to push it upstream. The command for this is simple: git push <remote> <branch>. If you want to push your master branch to your origin server (again, cloning generally sets up both of those names for you automatically), then you can run this to push any commits you’ve done back up to the server:
```
git push origin master
```

This command works only if you cloned from a server to which you have write access and if nobody has pushed in the meantime.If someone pushed thier work and you pushed just after that then your push will be rejected as you need to fetch thier work and then push your changes.

##### Inspecting a Remote

For checking the information of a particular remote you can use:
```
$ git remote show origin
* remote origin
  Fetch URL: https://github.com/schacon/ticgit
  Push  URL: https://github.com/schacon/ticgit
  HEAD branch: master
  Remote branches:
    master                               tracked
    dev-branch                           tracked
  Local branch configured for 'git pull':
    master merges with remote master
  Local ref configured for 'git push':
    master pushes to master (up to date)
```

It lists the URL for the remote repository as well as the tracking branch information.

##### Renaming and Removing Remotes
you can use rename command to rename your git remote.For example:
```
$ git remote rename pb paul
$ git remote
origin
paul
```

For some reason if you want to remove the remote e.g., some person is not contributing anymore then use remove/rm command.
```
$ git remote remove paul
$ git remote
origin
```
