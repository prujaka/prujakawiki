Create a new branch starting from `dev`:

```zsh
git checkout dev
git checkout -b category/branch_name
```

Then, make several commits.

Say, `123abc` is the short hash of the **first** commit in the branch commit history, and you want to squash all the commits that follow. To do so, rebase the current branch by the following command:

```zsh
git rebase -i 123abc~1
```

An text editor will open with the following lines:

```
pick 123abc commit message 1
pick 456def commit message 2
pick 789ghi commit message 3
```

You can only glue your commits to the top commit `123abc`, so replace all `pick` with `squash`, except the top one, and put the `commit message 1` instead of the `commit message 3`:

```
pick 123abc commit message 3
squash 456def commit message 2
squash 789ghi commit message 3
```

Then, save and exit. Another editor window will pop up and propose you to enter the commit message for the squash commit. Erase everyting before the lines:

```
# Please enter the commit message for your changes. Lines starting 
# with '#' will be ignored, and an empty message aborts the commit. 
```

and type your commit message without the `#` before:

```zsh
new commit message

# Please enter the commit message for your changes. Lines starting 
# with '#' will be ignored, and an empty message aborts the commit. 
```

Save and exit. Then merge the new branch with `dev`:

```zsh
git checkout dev
git merge category/branch_name
(git push origin dev)
git branch -d category/branch_name
```

After you repeat everything several times and feel that you're ready for a new release on the `main` branch, make a pull request on the github, checkout to main and tag the new release:

```zsh
git checkout main
git pull
git tag -a 0.1 -m "my version 0.1"
git push 0.1
```

