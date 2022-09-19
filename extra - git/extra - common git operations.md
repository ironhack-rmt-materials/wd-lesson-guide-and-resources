

<!-- Status: draft -->



## Branches

Create a new branch: 
- `git checkout -b myNewBranch`: creates a new branch "myNewBranch" & moves to that branch


Switch to a different branch: 
- `git switch branchName`


Integrate changes from one branch to another:
- `git merge branchName`: integrates changes from "branchName" in the current branch



## Undo changes

Revert a specific commit:
  - `git revert commitId` (creates a new commit with the opposite changes)



## Travel in time

`git checkout commitId `
→ move my file system to a previous state
→ "travel in time only for temporal testing (we dont change git status)"
→ note: we would be in "detached head" state (if you want to go back to normal state, use 'git switch -')

`git switch -` 
→ come back to previous state
→ go back to normal state

`git reset --hard commitId `
→ change the status of git to a previous commit
→ "travel in time and change git status"

`git reset --hard origin main `
→ reset your local respository with the contents in "origin"
→ warning: you will loose all the changes in your local repo (anything that is not in the remote repo)


## Bonus

Cherry pick:
  - `git cherry-pick commitHash`