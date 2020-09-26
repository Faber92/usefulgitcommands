## Rebase

### Rebase current branch since diverged from <branch_name>
```
git rebase [-i] <base_branch_name> [<branch_name>]
```

###### Before
```
a---b---c---d---e  master
         \
          f---g---h  feature1
```

###### Command
```
git rebase master [feature1]
```

###### After
```
a---b---c---d---e  master
                 \
                  f'--g'--h'  feature1
```

### Rebase current branch starting from <commit_hash>
```
git rebase -i <commit_hash>
```

### To apply all your yet-to-be-pushed commits on top of the remote tree commits. Basically a git fetch and then git rebase on remote.
```
git pull --rebase
```

### To move hunks between commits while rebasing

###### Edit the todo list during an interactive rebase.
```
git rebase --edit-todo
```

###### Mark commits from the list that you want to edit
```
edit <commit_hash>
```

###### Rewind HEAD by one
```
git reset HEAD^ [<file_name>]
```

###### Stage and commit the changes you choose
###### You may stash changes if you want to merge the hunks with later commits

### Rebase branch forking point
```
git rebase --onto <new_base_branch_name> <old_base_branch_name> [<branch_name>]
```

###### Before
```
a---b---c---d---e  master
         \
          f---g---h---i---j  feature1
                           \
                            k---l---m  feature2
```

###### Command
```
git rebase --onto master feature1 [feature2]
```

###### After
```
a---b---c---d---e  master
        |        \
        |         k'--l'--m'  feature2
         \
          f---g---h---i---j  feature1
                           \
                            k---l---m  feature2@{1}
```

### Rebase branch and its sub-branches

###### Before
```
a---b---c---d---e  master
         \
          f---g---h---i---j  feature1
                           \
                            k---l---m  feature2
```

###### Command
```
git rebase master [feature1]
```

###### Between
```
a---b---c---d---e  master
        |        \
        |         f'--g'--h'--i'--j'  feature1
         \
          f---g---h---i---j  feature1@{1}
                           \
                            k---l---m  feature2
```

###### Command
```
git rebase --onto feature1 feature1@{1} [feature2]
```

###### After
```
a---b---c---d---e  master
        |       \
        |        f'--g'--h'--i'--j'  feature1
        |                         \
        |                          k'--l'--m'  feature2
         \
          f---g---h---i---j  feature1@{1}
                           \
                            k---l---m  feature2@{1}
```
