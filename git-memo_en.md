# Git (WIP)



![execution-context](_readme-img/git/git-logo.png)



\```markdown

| Project: Git  | Document type: Memo | Author: Vincent Chilot | Last revision: 16/11/2020 |

\```

## Link repository

```
echo "# my-repo >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M master
git remote add origin git@github.com:Raigyo/webpack-react-hot-reload.git
git push -u origin master
```


​                
…or push an existing repository from the command line

```
git remote add origin git@github.com:Raigyo/webpack-react-hot-reload.git
git branch -M master
git push -u origin master
```

## Git commands

`git init`

`git add .`

`git add <file-name>`

`git commit -m "Initial commit"`

`git status `

`git fetch`

`git merge <otherbranch>`

### Clone

git clone <my-repo>

git clone <my-repo> <directory>

git clone -b <mybranch> <my-repo>

### Remote

`git remote add origin <my-repo>`

`git remote set-url origin <my-repo>`

`git remote -v`

`git remote rm origin `

`git remote set-url origin ssh://git@github.com/user/repo.git`



### Pull

`git pull origin master`

`git pull origin master --allow-unrelated-histories`

### Push

`git push origin master`

`git push -u origin <branchname>`

### Checkout

`git checkout -b <newbranch>`

`git checkout <tobranch>`

`git diff <FIRST-BRANCH>..<SECOND-BRANCH>`

`git branch -d <BRANCH-TO-DELETE>`

`git branch -m <OLD-BRANCH-NAME> <NEW-BRANCH-NAME>`

### Stash

`git stash`

`git stash list`

`git stash apply`

`git stash apply --<filename>`

### Remove

`git rm -r --cached <file/>`

`git rm -r --cached <foldername/>`

`git rm -r --cached node_modules`

`git commit -m "removing node_modules"`

`touch .gitignore && echo "node_modules/" >> .gitignore && git rm -r --cached node_modules`

`git status`

## Problem with remote

`git remote rm origin `

`git remote add origin git@github.com:user/repo.git`

`git push origin master`


## Delete a remote branch
`git push origin --delete <branch>` # Git version 1.7.0 or newer 

`git push origin :<branch>` # Git versions older than 1.7.0

## Delete a local branch
`git branch --delete <branch>`

`git branch -d <branch>` # Shorter version

`git branch -D <branch>` # Force delete un-merged branches

## Delete a local remote-tracking branch
`git branch --delete --remotes <remote>/<branch>`

`git branch -dr <remote>/<branch>` # Shorter

`git fetch <remote> --prune` # Delete multiple obsolete tracking branches

`git fetch <remote> -p` # Shorter

------------

## GIT LARGE FILE STORAGE

http://arfc.github.io/manual/guides/git-lfs

## Problem with gitignore

Remove the cache of all the files

`git rm -r --cached .`

Remove the cache of specific file

`git rm -r --cached <file_name.ext>`

Once you clear the existing cache, add/stage file/files in the current directory and commit

`git add .`  # To add all the files
`git add <file_name.ext>` # To add specific file
`git commit -m`  "Suitable Message"

## Heroku

`git remote rm heroku`
`git remote add heroku git@heroku.com:repo.git`