###Basic Commands For Branching & Merging:

What is a branch in git?

1.)**git branch branch_name**: To create a branch.

2.)**git checkout branch_name**: To switch to another branch named branch_name.

Why to write 2 commands?
- we can use **git checkout -b branch_name**, this command will create and switch you to that branch.

3.)**git branch**: To list all the branches that are present in your local.* indicates the current present.

How git knows in which branch you are currently in?

4.)**git branch flag**: 
 
 -v flag will list all the branch with their last commit.
 --merged flag will list down all the merged branch which you can delete safely.
 --no-merged flag will list down all the unmerged branch.
 
5.)**git merge branch_name**: If your current branch is A then this command will merge specific branch to branch A.So branch A will have all the updated changes.

###Scenario 1: 

![](../images/basic-branching-3.png)

You need to merge **iss53** branch to master.

1.)How to achieve the above scenarios?

2.)After merging the **iss53** branch can we delete it?

3.)If we can delete it, then how commits and its parents will be changed in the image.

4.)How git internally handles it?


###Scenario 2:

![](../images/basic-branching-7.png)

Now the case is different here, because the commit on the branch you’re on isn’t a direct ancestor of the branch you’re merging in, Git has to do some work.

1.)How to achieve the above scenarios?

2.)How the commits and its parent will be changed in the image?

3.)How git internally handles it?

###Scenario 3: 
Explain the conflicts scenario.

How to delete a local branch & remote branch? 

