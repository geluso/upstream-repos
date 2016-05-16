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

## Create A New Branch For Each New Feature

```
git checkout -b new-feature-branch
```

Create files, edit files on this branch and then add and commit them normally.

```
git add -A
git commit -m "finished new feature"
```

## Pulling
Now you're ready to switch back to the master branch to pull in everyone
else's new changes.  There may be merge conflicts. Resolve them.

```
git checkout master
git pull upstream master
```

## Bringing In Remote Changes

Checkout your new feature branch again to merge the changes from the
remote source into your new feature branch. It's good to have both
the master branch and the new-feature-branch so you can pull in changes
to master in a place unaffected by your current changes.

```
git checkout new-feature-branch
git merge master
```

Now you have merged changes from upstream to both your master branch,
and to your new-feature-branch.

## Publishing Your Changes To The Remote Source
When your feature is complete you need to publish your changes to everyone
else by pushing them.

```
git checkout master
git pull upstream master
# resolve conflicts from bring remote changes to master
git merge new-feature-branch
# resolve conflicts from merging our changes onto master
git push upstream master
```

Notice that we always pull from upstream master before pushing to
upstream master. This is a good practice where we're always checking
to see if there are new changes. We can't push any of our own changes
until we have all of the newest changes from the server.
