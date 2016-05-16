# Upstream Practice
This repo is for practicing upstream pulling and pushing.

## Initial Set Up
* Log in to GitHub and fork this branch.
* Clone your fork to your own computer.
* Change to inside the directory of your fork.
* Now run this command to add a reference to the upstream repo

Replace `[[ORIGINAL_REPO_OWNER]]` and `[[REPO_NAME]]` with the GitHub user
name of the original owner, and the name of the repo.

```
git remote add upstream git@github.com:[[ORIGINAL_REPO_OWNER]]/[[REPO_NAME]].git
```

## Pulling
```
git pull upstream master
git checkout new-feature-branch
git merge master
```

## Pushing
```
git checkout master
git pull upstream master
git merge gus
git push upstream master
```

Then go to GitHub and create a pull request
