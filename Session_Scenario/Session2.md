### Basic Commands For Branching & Merging:

What is a branch in git?

1.) **git branch <_branch_name_>**: To create a branch.

2.) **git checkout <_branch_name_>**: To switch to another branch named branch_name.

Why to write 2 commands?
- we can use **git checkout -b <_branch_name_>**, this command will create and switch you to that branch.

3.) **git branch**: To list all the branches that are present in your local.* indicates the current present.

How git knows in which branch you are currently in?

4.) **git branch <_flag_>**: 

    | Flag       | Use                                                          |
    |------------|-:------------------------------------------------------------|
    | -v         | list all the branch with their last commit.                  |
    | --merged   | list down all the merged branch which you can delete safely. |
    | --no-merge | list down all the un-merged branch.                          |
 
5.) **git merge <_branch_name_>**: If your current branch is A then this command will merge specific branch to branch A.So branch A will have all the updated changes.

### Scenario 1: 

![](../images/basic-branching-3.png)

You need to merge **iss53** branch to master.

1.) How to achieve the above scenarios?

2.) After merging the **iss53** branch can we delete it?

3.) If we can delete it, then how commits and its parents will be changed in the image.

4.) How git internally handles it?


### Scenario 2:

![](../images/basic-branching-7.png)

Now the case is different here, because the commit on the branch you’re on isn’t a direct ancestor of the branch you’re merging in, Git has to do some work.

1.) How to achieve the above scenarios?

2.) How the commits and its parent will be changed in the image?

3.) How git internally handles it?

### Scenario 3: 
Explain the conflicts scenario.

How to delete a local branch & remote branch? 

