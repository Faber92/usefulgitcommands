## Cherry-pick

### Cherry pick a single commit
```
git cherry-pick <commit_hash>
```

### Cherry pick a single commit (no commit is made)
```
git cherry-pick -n <commit_hash>
```

### Cherry pick multiple commits

###### (older commit not included)
```
git cherry-pick <older_commit_hash>..<newer_commit_hash>
```

###### (older commit included)
```
git cherry-pick <older_commit_hash>^..<newer_commit_hash>
```

### Cherry pick editing commit message
```
git cherry-pick -e <commit_hash>
```

### Reference cherry picked commit(s)
```
git cherry-pick -x <commit_hash>
```

```
git cherry-pick -x <older_commit_hash>..<newer_commit_hash>
```

```
git cherry-pick -x <older_commit_hash>^..<newer_commit_hash>
```

### Cherry pick a merge commit

###### From first parent
```
git cherry-pick -m 1 <commit_hash>
```

###### From second parent
```
git cherry-pick -m 2 <commit_hash>
```
