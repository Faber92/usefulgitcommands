## Remove all merged branches locally:
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
git_print_merged_in() { git fetch -p && git checkout $1 && git branch --merged | egrep -v "(^\*|master|develop)"}

git_print_merged_in() {  git fetch -pq && git checkout $1 -q && for branch in `git branch --merged | egrep -v "(^\*|master|develop)"`; do echo "Would remove branch '$branch'"; done }
```

## Remove all merged branches locally:
```
git_remove_merged_in() { git fetch -p && git checkout $1 && git branch --merged | egrep -v "(^\*|master|develop)" | xargs git branch -d }

git_remove_merged_in() { git fetch -pq && git checkout $1 -q && for branch in `git branch --merged | egrep -v "(^\*|master|develop)"`; do echo "Removing branch '$branch'"; git branch -d $branch; done }
```

## Ahead/Behind commit count
```
git status -sb | egrep 'ahead|behind' | awk '{ print $3 " " $4 }' | tr -d '[|]'
```
