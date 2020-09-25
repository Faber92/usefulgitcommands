## Stash

### To save a stash
```
git stash [save "stash_name"]
```

### To list stash entries
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

### To apply the last stash entry without removing it from the list
```
git stash apply
```

### To apply a specific stash entry without removing it from the list
```
git stash apply stash@{stash_number}
```

### To apply and remove the last stash entry
```
git stash pop
```

### To apply and remove a specific stash entry
```
git stash pop stash@{stash_number}
```

### To remove the last stash entry
```
git stash drop
```

### To remove a specific stash entry
```
git stash drop stash@{stash_number}
```