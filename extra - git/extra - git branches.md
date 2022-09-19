

# Git branches




## Intro

- Explain what are branches & why they're useful
  - Diagram 1 (simple): https://miro.medium.com/max/1400/1*BtNarpOHR5BxkMvbqfzqnw.png
  - Diagram 2 (complex): https://miro.medium.com/max/1110/0*4l_7lT1qH1wv7I99.png


- See useful commands (`\extra - common git operations.md`)


## Demo


How: 
- on a repo 
- or here: https://git-school.github.io/visualizing-git/


Example:

1. git checkout -b <branchname> --> create branch and move to it.

2. make commit(s) in the new branch

3. git checkout main --> move again to the main branch

4. git merge <branchname> --> merge code from "branchname" into current branch


If we want to continue working on "develop"...
- git checkout develop --> move again to "develop" branch
- make commit(s)
- repeat points 3. and 4.



## Git Workflows

Some common strategies ("workflows"):

- Trunk-Based Development (TBD)
  - main + develop + feature branches
  - Trunk (main) is deployable at all times. 
  - > In trunk-based development the main branch is assumed to always be stable, without issues, and ready to deploy.

- Git flow:
  - https://nvie.com/img/git-model@2x.png


Note: 
- Those are just some examples.
- Each team/product has different needs and policies.
  - ex. how code is merged onto the main branch (code review, PR, ...)





## Extra resources to practice git branches:

Visualizing Git: 
- a playground where you can try commands and see a diagram with the result
- https://git-school.github.io/visualizing-git/

Learn Git Branching
- guided tutorial to learn about git branches
- https://learngitbranching.js.org/


