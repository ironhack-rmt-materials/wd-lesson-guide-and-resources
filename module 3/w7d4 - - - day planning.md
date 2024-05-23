

# w7d4



## Day planning

- LAB Q&A [20m]

- Refresh main contents we've seen this week [40m]
  - routes
  - req.params, req.query, req.body
  - mongoose
    - schema, model
    - mongoose methods

    <!-- alternative: provide a 30m. recording -->


- Refresh / Explain: relationships + populate [1h]
  - type of relationships (1:1, 1:many, many:many)
  - embedded documents
  - references
  - recommendations


- (extra) intro github copilot [20m]


- explain: plan today + tomorrow.


- (skip) Ironlauncher
  <!-- @LT: do this w8d2 instead -->


- Intro to "Express | REST API" [1h]
  - see list of topics to cover below


- (Self-guided) Express | REST API
  - see notes below.

  

## Intro to "Express | REST API"

Refresh REST [10min.]
- slides: https://docs.google.com/presentation/d/194i1dCV2vpqTN5T3yC5lysvfS-_fnEkok97QpaOtb3w/edit?usp=sharing


Explain: how to extract routes to specific files
- Explain on the app from yesterday.
- example: https://github.com/ironhack-jan2024-AngryCats/project-management-server/tree/main/routes


Explain: some other topics that they'll find in "Express | REST API"
- push: `Project.findByIdAndUpdate(projectId, { $push: { tasks: newTask._id } }`
- Validation: `mongoose.Types.ObjectId.isValid(projectId)` (check if format is valid, even if it doesnt exist in the db)


Mention "IronLauncher"
- In the unit "Express | REST API", the initial code is created with ironlauncher




## Active Learning / Afternoon


1. "Express | REST API"
    - Follow the steps in this unit, starting from the section "Project Management API"
    - How: groups of 2-3 (same groups that we use for mini-project)

2. Mini Project - REST API - Day 4


3. Watch Recording "Auth: intro and hash algorithms" (1h): https://www.loom.com/share/99e0abae2c9346a3ba84d1e178c06b48?sid=e471b840-b8a6-44a1-9070-4f5a5f662518


Bonus: 
- Implement your routes with `async/await` instead of `.then().catch()`


Also:
- Submit project preferences
  - Deadline: tomorrow 10am.



