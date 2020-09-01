# usefulgitcommands
Useful Git Commands I discovered so far.



### Remove all merged branches locally:
```
git fetch -p && for branch in `git branch -vv | grep ': gone]' | awk '{ print $1 }'`; do git branch -D $branch; done

git fetch -p && git branch -vv | grep ': gone]' | awk '{ print $1; }' | xargs git branch -d
```


## Rename branch:

###### 1) Rename branch locally
```
git branch -m old_branch new_branch
```

###### 2) Delete the old branch
```
git push origin :old_branch
```                 

###### 3) Push the new branch, set local branch to track the new remote
```
git push --set-upstream origin new_branch
```

## Print all merged branches locally:
```
git_print_merged_in() { git fetch -p && git checkout $1 && git branch --merged | egrep -v "(^\*|master|Develop)"}

git_print_merged_in() {  git fetch -pq && git checkout $1 -q && for branch in `git branch --merged | egrep -v "(^\*|master|Develop)"`; do echo "Would remove branch '$branch'"; done }
```

## Remove all merged branches locally:
```
git_remove_merged_in() { git fetch -p && git checkout $1 && git branch --merged | egrep -v "(^\*|master|Develop)" | xargs git branch -d }

git_remove_merged_in() { git fetch -pq && git checkout $1 -q && for branch in `git branch --merged | egrep -v "(^\*|master|Develop)"`; do echo "Removing branch '$branch'"; git branch -d $branch; done }
```


## Tags

### Create a tag locally
```
git tag `tagname`
```

### Remove a tag locally
```
git tag --delete `tagname`
```

### Push a tag remotely
```
git push origin `tagname`
```

### Remove a tag remotely
```
git push --delete origin `tagname`
```


## Stash

### To list stashes
```
git stash list
```

### To show files changed
```
git stash show stash@{stash_number}
```

### To show content of files changed
```
git stash show -p stash@{stash_number}
```


## Sign commits

### To configure your Git client to sign commits by default for a local repository
```
git config commit.gpgsign true
```

### To sign all commits by default in any local repository on your computer
```
git config --global commit.gpgsign true
```


## Ahead/Behind commit count
```
git status -sb | egrep 'ahead|behind' | awk '{ print $3 " " $4 }' | tr -d '[|]'
```


## Rebase

### To apply all your yet-to-be-pushed commits on top of the remote tree commits allowing your commits to be straight in a row and without branches
```
git pull --rebase
```


## Cherry-pick

### Cherry pick single commit
```
git cherry-pick <hash>
```

### Cherry pick multiple commits

###### (A not included)
```
git cherry-pick A..B
```

###### (A included)
```
git cherry-pick A^..B
```

### Reference cherry picked commit(s)
```
git cherry-pick -x <hash>
```

```
git cherry-pick -x A..B
```

```
git cherry-pick -x A^..B
```


## Rerere

http://scottchacon.com/2010/03/08/rerere.html
