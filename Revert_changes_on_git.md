# Revert changes on git

### Revert changes from working directory
```sh
   git restore <file_name> 
          or
   git checkout -- <file_name>
```
- `Note: even you can remove changes manually. But if we have updated multiple files and don’t know which lines to remove this command really helps`

### Revert changes from Staging Area
```sh 
   git restore --staged <file_name>  #to revert changes from Staging area to working directory  
   git restore <file_name> #to revert changes from working directory  
```

### Revert changes from Local Repository 
```sh 
   git reset HEAD~         # to revert changes from local repo to working directory
   git restore <file_name(s)> # to revert changes from working directory  
```

### Revert changes from Remote Repository 

We dont have direct way to do this.

## 1. Soft Reset (Undo the commit but keep changes staged).
  + This will reset your commit and keep your changes in the staging area.
  + git reset --soft HEAD~1
  + HEAD~1 refers to the commit before the latest one.
  +  --soft keeps your changes staged for the next commit.
## 2. Mixed Reset (Undo the commit and unstage the changes)
  + If you want to reset your commit and move the changes to the working directory (unstaged), use:
  + git reset --mixed HEAD~1: Undo the commit and unstage the changes (default option).
  + HEAD~1 refers to the commit before the latest one.
  + --mixed is the default option and will keep your changes in the working directory but unstaged.

## 3. Hard Reset (Undo the commit and discard changes) 
  + git reset --hard HEAD~1: Undo the commit and discard all changes in the working directory.
  +  Hard Reset (Undo the commit and discard changes)
  +  git reset --hard HEAD~1
  +  HEAD~1 refers to the commit before the latest one.
  +  --hard discards all changes in the working directory and the staging area.
