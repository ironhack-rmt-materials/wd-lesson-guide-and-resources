

# Github projects (kanban):


## Setup

Your GitHub profile -> Projects -> 'New Project'

- Add project name
- Template -> Automated Kanban


## Start adding tasks

Go back to the repository -> Issues -> New Issue

- Add Issue Title
- to create checklist, EXACT syntax would be:
  (dash + space + bracket + space + bracket)

	- [ ] one
	- [ ] two

- One the right side of the screen
	- Assignees - assign yourself
	- Projects -> select current project
	- option to add labels + customise them

To view the planning board, you need to go back to your profile -> projects


## EXTRA: Link git commit to tasks completed

In terminal:

- git add .
- git commit -m "completed demo task resolve #4" // you have to type 'resolve' + hash + issue's number // number is automatically added when you create issue
- git push origin main