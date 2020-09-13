Intro to GitHub: 
basic workflo of git --> modifying files --> staging changes --> commiting --> deleting etc

What is GitHub: distributed VCS
distributed: each developer has a copy of the whole repository on their local machine
each copy is peer of others but we host one of these copies on a server and use it as remote repo for other copies
GitHub is web based repository hosting service. features like bug tracking, wikis, and task management
copy or *clone* them to our local computer to work on them.

Basic interactions with GitHub:
1. creation of repo
2. create local copy by clicking Clone and copy address
3. git clone copied link of repo
4. cd reponame
5. ls -l
6. atom README.md --> markdown file is opened after adding content commit
7. git commit -a -m "Add one more line"
we can send changes to repository using push
8. git push asks for password and done
retrieving the repo and when pushing changes to repo
SSH key-pair, Credential helper for this we need to enable 
9. git config --global credential.helper cache
to check the cached file we use pull which is use to retrieve new changes from the repository
10. git pull 

What is remote: the remote repo is big part of the distributed nature of Git collaboration. increase privacy, control 
If you have your own local changes when you pull down the code from the remote repo, you might need to fix merge conflicts before you can push your own changes. In this way Git let's multiple people work on the same project at the same time. When pulling new code it will merge the changes automatically if possible or will tell us to manually perform the integrating if there are conflicts.
modify --> stage --> commit --> fetch --> merge --> push 
HTTP --> read only access, SSh and HTTPS --> provide methods of authenticating so we can control

Working with remotes:
git clone: sets the copy of remote repo with default origin name locally
1. cd reponame
2. git remote -v we will get two links one is fetch(for HTTP --> read only) other one is push(HTTPS or SSH --> access control)
local is origin to get info 
3. git remote show origin
4. git branch -r --> shows the running branches which are read only but we cant change any content in them

Fetching new changes: 
1. cd reponame
2. git remote show origin --> we can see the repo changes which are not reflected locally
to sync the data we use git fetch
3. git fetch --> downloads the changes automatically to our local repo
4. git log origin/master
5. git merge origin/master --> merges all branches to master(Fast-forward)
git pull download changes and merges to master whereas git fetch downloads the changes but doesn't updated to master

Updating Local Repo:
1. git pull --> git fetched the updated contents from the remote repo including new branch and use fast-forward to merge to master branch
2. we can see changes using git log -p -1
3. git remote show origin --> shows the repos in git 
4. git checkout experimental --> copies to local branch

The Pull-Merge-Push Workflow:
1. atom file.py --> made changes to file
2. git add -p
3. git commit -m "Message"
4. git push --> thsi can give error if the file is not saved locally for this we use git pull 
5. git log --graph --oneline --all --> this shows all commits and positions in tree
6. git log -p origin/master
conflict marks >>>>>
7. atom file.py after setting the changes
8. git add file.py
9. git commit -m "message"
10. git push

Pushing remote branches:
1. git checkout -b refactor --> started working on refractor
2. atom file.py made changes
3. git commit -a -m 'Mesage'
4. git push -u origin refractor

Rebasing your changes: git rebase --> changin the base commit that is used for our branch, 
1. git checkout master
2. git pull
3. git log --graph --online --all shows the rfractor changes
4. git checkout refractor
5. git rebase master
6. git checkout master 
7. git merge refractor
8. git push --delete origin rfractor

Another rebasing: order commits, alternate for merge
One for merging feature branches back into the main trunk of our code and one for making sure that our commits made in the master branch apply cleanly on top of the current state of the master branch and it doesn't stop there.

collaborating: synchronizing the branches before work starts
This lets you work on new changes while still enabling you to fix bugs in the other branch.
Regularly merge changes made on the master branch back onto the feature branch.
have the latest version of the project in the master branch and a stable version of the project on a separate branch.
you shouldn't rebase changes that have been pushed to remote repos.