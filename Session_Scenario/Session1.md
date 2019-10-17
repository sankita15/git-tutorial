### Basic Commands:

1.) **git remote -v**: will lists all the names of each remote handle you’ve specified.By default remote is origin.
```text
$ git remote -v
origin	https://github.com/schacon/ticgit (fetch)
origin	https://github.com/schacon/ticgit (push)
```

2.) **git remote add <_short_name_> <_url_>**:To add remote git repository as a short name.

![](../images/areas.png)

3.) **git clone <_url_>**: To clone an existing repositories.**(.git repository)**

3.) **git fetch <_remote_name_>**: To fetch all the information from a specific remote.
Note: It will just fetch the information, it will not merge in your working directory.

4.) **git pull origin master**: To pull information from master branch.

5.) **git push origin master**: To push information to master(upstream).(Pushing your master branch to origin server)

6.) **git add <_file_path_>**: To add the specific file to your staging area.(working directory to staging area)

7.) **git commit -m <_commit_msg_>**: To locally commit your staged work.**(staging area to .git repository)**

8.) **git checkout <_file_path_>**: To remove the changes present in our working directory.(changes will be gone)

9.) **git reset <_file_path_>**: To move the ```file_path``` from staging area to working directory.(changes will be un staged)

### Scenario 1: 

_Assumption:- You have 3 files in your repository. you need to add them and then commit them locally_

1.) What happens internally in git when you add or staged any file changes from your working directory?

2.) What happens internally in git when you commit your staged changes? 

3.) How to revert the locally committed change? (version - no one knows)

4.) How to revert it if its the initial commit :wink: 😉