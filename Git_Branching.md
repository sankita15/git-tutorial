## Git Branching - Branches in a Nutshell

* As we know, Git doesn’t store data as a series of changesets or differences, but instead as a series of snapshots.

* What happens when you add or stage a file?
    - Staging the file will create a checksum or SHA-1 hash for each file and stores the version of file in git repository, then adds that checksum to the staging area.
    (In short creates checksum and put that checksum in staging area).
    
* What happens when you commit a file?
    - Git creates and store a **commit object** that contains a pointer to the snapshot of content you staged.
    - This commit object stores author’s name and email address, the message that you typed, and a pointer for parent object(no parent in case of initial commit, one parent incase of normal commit and more than 1 parent in case of merge commit)
    
    
Let understand this by an example:
You have some changes and you need to add a file.
```text
$ git add README test.rb LICENSE
```
Git computes the checksum for each file which is known as **blobs**.
Then these blobs will get added to staging area.

Now we will commit the changes:
```text
$ git commit -m 'The initial commit of my project'
```

Git will now create a checksum for each subdirectories(one in this case) and stores them in a tree object in git repository.
Git then creates a commit object that has the metadata and a pointer to the root project tree so it can re-create that snapshot when needed.

**Now your git object is having 5 objects:**
1. 3 blobs referring to each file.
2. one tree that lists the contents of the directory and specifies which file names are stored as which blobs.
3. one commit with the pointer to that root tree and all the commit metadata.

![](images/commit-and-tree.png)

If you make some changes and commit again, the next commit stores a pointer to the commit that came immediately before it.

![](images/commits-and-parents.png)


**Notes: A branch in Git is simply a lightweight movable pointer to one of these commits.The “master” branch in Git is not a special branch. It is exactly like any other branch. The only reason nearly every repository has one is that the git init command creates it by default and most people don’t bother to change it.**


##### Creating a new branch
Creating a new branch means just to create a new pointer on the last commit from where you are creating a branch.
```text
$ git branch testing
```

And git maintains a special pointer named HEAD which indicates the current branch your are in.

![](images/head-to-master.png)

This images indicate that HEAD(your current position) is master and you created a new branch(a new pointer) testing from master.
 
##### Switching branches
Switching branch means moving the pointer HEAD from one branch(pointer) to other.
To switch a branch, you need to use:
```text
$ git checkout testing
```

Suppose we did some commit in testing branch and now moving to master branch. So the commands will be:
```text
$ vim test.rb
$ git commit -a -m 'made a change'
$ git checkout master
```

![](images/checkout-master.png)

- So here testing branch is at the commit we did and as we checkout to master in the image, HEAD is at master.
* checkout command here does 2 things moved the HEAD back to master and reverted the changes to the snapshot where master points to in your working directory. 


Lets suppose if I will do some commits in the master branch then you will have a divergent git history.
![](images/advance-master.png)

