To work on your project do the following:

1. Clone down this repository: `git clone git@github.com:BW-Saltiest-Hacker-News-Trolls/saltiest-hacker-news-trolls.git`
2. Run `git submodule init`: `git submodule init`
3. Run `git submodule update`: `git submodule update`.
4. `cd` into your specific repository.  E.g., `cd flask_modeling`
5. Add an `upstream` remote to the repository: `git remote add upstream <URL>`
6. Now, you can work on your project within the submodule.  When you're ready to push run the following:
```
git push upstream master
git checkout master
cd ..
git add .
git commit -m 'Update submodule <submodule>'
git push origin master
```
7. Done!
8. To keep everyone else's changes up to date, `cd` out of your submodule and
   into the main repo and run:
```
git pull
git submodule update
cd <your_submodule>
git checkout master
```
You will want to run the last step after pushing to `upstream` but before
checking out `master` in order to avoid merge conflicts.

If you do happen to run into a merge conflict, you can always restore the repo
by pushing your submodule to upstream, then deleting the main repository `rm -r
saltiest-hacker-news-trolls` and re-cloning:
```
git clone git@github.com:BW-Saltiest-Hacker-News-Trolls/saltiest-hacker-news-trolls.git
cd saltiest-hacker-news-trolls
git submodule init
git submodule update
cd <your_submodule>
git remote add upstream <URL>
git checkout master
cd ..
git add .
git commit -m 'Update submodule <submodule>'
git push origin master
```

If you want to use a separate branch (other than `master`), your workflow will look like:
```
cd <submodule>
git checkout <branch_name>
git push upstream <branch_name>
# Ready to push your changes to the main repo
cd ..
git pull
git submodule update
cd <submodule>
git checkout master
git merge <branch_name>
git push upstream master
git checkout master
cd ..
git add .
git commit -m 'Update submodule <submodule>'
git push origin master
```
