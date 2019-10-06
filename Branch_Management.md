## Branch Management

```text
$ git branch
  iss53
* master
  testing
```

* git branch command will list you all the branches that are present in your local. *(star) icon indicates the position of current branch(HEAD).
* -v flag will list all the branch with thier last commit.

```text
$ git branch -v
  iss53   93b412c fix javascript issue
* master  7a98805 Merge branch 'iss53'
  testing 782fd34 add scott to the author list in the readmes
```

* --merged flag will list all the branches that got merged to master and can be safely deleted.

* --no-merged flag will show all the branches which are present in your local but yet to be merged.