#### Steps to Add a Git Tag
 Create a Lightweight Tag

 ```
git tag -a v1.0 -m "Release version 1.0"
```

## Tag a Specific Commit
```
git tag <tagname> <commit>
git tag v1.0 9fceb02
```

## Listing Tags
To see all the tags in your repository, use:
```
git tag
```
For more detailed information:
```
git show <tagname>
git show v1.0
```

## Pushing Tags to Remote Repository
```
git push origin <tagname>
git push origin v1.0
```
Push All Tags
```
git push origin --tags
```

## Deleting a Tag
Delete a Local Tag
```
git tag -d <tagname>
git tag -d v1.0
```
Delete a Remote Tag
First, delete the local tag:
```
git tag -d <tagname>
```
Then, delete the tag from the remote repository:
```
git push origin --delete <tagname>
git push origin --delete v1.0

```

