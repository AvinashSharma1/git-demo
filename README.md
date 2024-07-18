# Summary of the Process
  ## 1. Feature Branch Workflow:
  +  Create feature/ISV-101 from develop.
  +  Push feature/ISV-101 to remote.
  +  Create a PR to merge feature/ISV-101 into develop.
  +  Integrate Changes to test:
  
  ## 2. Create merge-develop-into-test from develop.
  +  Push merge-develop-into-test to remote.
  +  Create a PR to merge merge-develop-into-test into test.
  +  Deploy Changes to prod:
  
  ## 3. Create merge-test-into-prod from test.
  + Push merge-test-into-prod to remote.
  + Create a PR to merge merge-test-into-prod into prod.

## Detailed Workflow
## 1. Create and Push Feature Branch:
  ``` git checkout develop
      git pull origin develop
      git checkout -b feature/ISV-101
      # Make changes
      git add .
      git commit -m "Implement feature ISV-101"
      git push origin feature/ISV-101
```
## 2. Create PR from feature/ISV-101 to develop:
  + Go to GitHub, create a PR from feature/ISV-101 to develop.
  + Get the PR reviewed, approved, and merged.
## 3.Merge develop into test:
  ```
    git checkout develop
    git pull origin develop
    git checkout -b merge-develop-into-test
    git push origin merge-develop-into-test
  ```
  + Create a PR from merge-develop-into-test to test.
  + Get the PR reviewed, approved, and merged.
## 4. Merge test into prod:
  ```
    git checkout test
    git pull origin test
    git checkout -b merge-test-into-prod
    git push origin merge-test-into-prod
  ```
  + Create a PR from merge-test-into-prod to prod.
  + Get the PR reviewed, approved, and merged.
## How to change Git author-name
# Start interactive rebase for the last 4 commits
git rebase -i HEAD~4

# In the editor, change `pick` to `edit` for each commit, then save and close

# For each commit Git pauses at:
git commit --amend --author="New Author Name <newemail@example.com>"
git rebase --continue

# After all commits are amended and the rebase is complete:
git push --force

    
