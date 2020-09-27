## Config

### Sign commits when committing by default
```
git config [--local | --global] commit.gpgSign true
```

### Choose your desired text editor
```
git config [--local | --global] core.editor <editor_name>
```

### Prefer rebasing over merging when pulling
```
git config [--local | --global] pull.rebase true
```

### Let rebase autostash your working tree while rebasing
```
git config [--local | --global] rebase.autoStash true
```
