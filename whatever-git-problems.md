# Whatever git/github problems I've ever encountered

If ever created a remote origin with a bad name:
`git remote remove origin`

Same for the link:
`git remote set-url origin git://new.url.here`

Changing the most recent commit message. Use --amend flag with the git commit command to commit again for changing the latest commit:
`git commit --amend -m "New commit message"`


#### Set up github on a new machine
Add global user name:
`git config --global user.name "User Name"`

Add global email address:
`git config --global user.email "user@email.com"`

If you don't want your personal email to be associated with configs:
1) Go to your github profile > "Settings" > Emails > check the box "Keep my email addresses private"
2) Add your github no-reply email to git config on your machine:
`git config --global user.name "ID+USERNAME@users.noreply.github.com"`

Clone a repo on the new machine
`git clone https://github.com/username/reponame.git`

Type your username;
Type your token.


#### Fetch the locally non-existing branch from remote:
The following command will create a local branch named daves_branch, tracking the remote branch origin/daves_branch. When you push your changes the remote branch will be updated.
`git checkout --track origin/revisions`
