## Rerere

### Enable the rerere functionality
```
git config --global rerere.enabled true
```

### Print resolutions that rerere will record
```
git rerere status
```

### Remove incorrect resolution for a file
```
git rerere forget <file_name>
```
