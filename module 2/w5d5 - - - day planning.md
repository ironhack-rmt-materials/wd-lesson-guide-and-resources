

# w5d5


<!-- @LT:  share day planning with students  -->


## Day planning:

- Presentations mini-project [1h]

- (in case we haven't done it yet) Some options to give CSS to React apps
  - see: `(extra) Some options to give CSS to React apps.md`

- Github organizations [20min.]
  <!-- @LT: follow steps in project-2 kickoff slides -->
  - start by creating repo in localhost (with Vite):
    - `npm create vite@latest our-cool-name -- --template react`
  - then, upload to github


- Git branches
  <!--
    First, explain merging branches without a conflict.
    Then, explain merging branches with a merge conflict.
  -->


- Git merge conflicts & how to solve them [1h]
  <!-- @todo: create self-guided lab (or video) so that they can do in pairs. -->


- Project kickoff [1h]
  
- Project planning (in pairs)

- Project planning session (in main room)


## Git merge conflicts

Slides: 
- https://docs.google.com/presentation/d/1G0RgvH93o_HT2mOZiotU9wkLNecdIDNGpIZJ1_ErZac/edit?usp=sharing



<!--
@todo:
- test with students + update slides
-->



<!-- 


Suggested path 1 (EASIER FOR STUDENTS ? -- test with them):

- git pull
  - "You have divergent branches and need to specify how to reconcile them"

- git config --global pull.rebase false
  - git will try to fast-forward; if not possible, it will create a merge commit.





Suggested path 2:

- git pull
  - "You have divergent branches and need to specify how to reconcile them"

- git config --global pull.ff only
  - Pull is fast-forwarded if possible, otherwise operation is aborted with an error message.

- git pull
  - "fatal: Not possible to fast-forward, aborting"

- git merge origin/main



-->


