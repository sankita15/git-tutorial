## How I set the documentation for git

* I created a new project in intelliJ and added my changes.

* I went to github and created a new private repository in my personal github account.

* As I already have a company account set up in my global gitconfig so I set up local git config specific to this repository.

* Enter the command - ```git config user.name "ankita sri"```

* Then - ```git config user.email "ankitacs0018@gmail.com"```

* For confirmation I checked in ```cat .git/config``` and saw for this repository I have different username and password other than gap account.

* Dont check use ```cat ~/.gitconfig``` as this will show global config details

* Every project will have .git folder where you can have project specific config file where you can set details, that's why we check here ```cat .git/config```

* Then we need to set the upstream information by running the following command - ```git remote add origin https://github.com/sankita15/Git_Notes.git```

* Then push your changes ```git push -u origin master```


# Deleting the initial commit:
```text
git update-ref -d HEAD
```

It will delete the named reference HEAD, so it will reset (softly, you will not lose your work) all your commits of your current branch.
