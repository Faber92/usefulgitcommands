## Tag

### Create a (light-weight) tag
```
git tag <tag_name>
```

### Create a tag with annotation

###### (annotation already provided)
```
git tag [-a] <tag_name> -m <annotation>
```

###### (will prompt for annotation)
```
git tag -a <tag_name>
```

### Remove a tag locally
```
git tag -d <tag_name>
```

### Push a tag remotely
```
git push origin [:refs/tags/]<tag_name>
```

### Remove a tag remotely
```
git push -d origin [:refs/tags/]<tag_name>
```
