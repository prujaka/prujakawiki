Here I have a repo:

```zsh
project/
└─── file.py
```

and let's say I have two branches: `dev` and `main`:

```zsh
git branch
```

```zsh
*dev
main
```

Now I want to make a new feature. For this I make a new branch from `dev`:

```zsh
git checkout dev
git checkout -b feat/print-hui
```

Code the feature, say:

```zsh
echo "print('hui')" >> file.py
```

Add, commit:
```zsh
git add file.py
git commit -m "add print hui"
```

Now going to `dev`, squash merge and push:
```zsh
git checkout develop
git merge --squash
git push origin develop
```

Then, make a pull request on a github.

Then, tag:

```zsh
git checkout main
git pull
git tag 0.1.0 -m "cool version"
git push origin 0.1.0
```

