## Stash

### Save a stash (-u to add also untracked files)
```
git stash [push -m "stash_name"]
```

### List stash entries
```
git stash list
```

### Show files changed in a stash (-p for content)
```
git stash show [-p] stash@{<stash_number>}
```

### Apply last stash entry (or a specific one) without removing it from the list
```
git stash apply [stash@{<stash_number>}]
```

### Apply and remove the last stash entry (or a specific one)
```
git stash pop [stash@{<stash_number>}]
```

### Apply the last stash entry (or a specific one) into a new branch
```
git stash branch <branch_name> [stash@{<stash_number>}]
```

### Remove the last stash entry (or a specific one)
```
git stash drop [stash@{<stash_number>}]
```

### Remove all stash entries
```
git stash clear
```
