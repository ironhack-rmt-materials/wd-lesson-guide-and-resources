

# fix - remove a file with credentials from git history



## Issue 


- You made a commit that included a file with some secret or credentials (ex. a password) + you pushed those changes to Github.

- Even if you make a commit removing the secret from that file, that secret is still part of the history of commits (so, potentially, anyone can see that).




## Solution


`$ git filter-branch --tree-filter 'rm -f ./path/to/passwords.txt' HEAD`

<!--
@note:
- this will re-write the entire history
- it may be worth to explore other options (ex. re-writing history only from a specific commit where the error was made)
-->

Documentation: https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History#_removing_file_every_commit



NOTE:
- git filter-branch rewrites history


⚠️ WARNING ⚠️

> git filter-branch has a plethora of pitfalls that can produce non-obvious manglings of the intended history rewrite (and can leave you with little time to investigate such problems since it has such abysmal performance). 

> its use is not recommended. 


