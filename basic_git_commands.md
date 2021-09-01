# clone all your repos to localhost

```sh
curl -si https://api.github.com/users/magento/repos | grep ssh_url | cut -d '"' -f4


curl -si https://api.github.com/users/BAStos525/repos | \
    grep ssh_url | cut -d '"' -f4 | xargs -i git clone {}

```

# sync your local fork repo with origin repo

```sh
git clone git@github.com:YOUR-USERNAME/YOUR-FORKED-REPO.git
cd into/cloned/fork-repo
git remote add upstream git://github.com/ORIGINAL-DEV-USERNAME/REPO-YOU-FORKED-FROM.git
git fetch upstream
git pull upstream master
git push
```
# to fork any repo
```sh
gh repo fork **repository** --clone=true
```

# to When you fork a project in order to propose changes to the original repository, you can configure Git to pull changes from the original, or upstream, repository into the local clone of your fork.

# To configure a remote repository for the forked repository:
`gh repo fork **repository** --remote=true`

# To specify the remote repository's name
`gh repo fork **repository** --remote-name "main-remote-repo"`

# Reset and sync local repository with remote branch
# Remember to replace origin and master with the remote and branch that you want to synchronize with.
`git fetch origin && git reset --hard origin/master && git clean -f -d`

