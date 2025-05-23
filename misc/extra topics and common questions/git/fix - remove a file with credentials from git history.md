

# fix - remove a file with credentials from git history



## Issue 


- You made a commit that included a file with some secret or credentials (e.g. a password) + you pushed those changes to Github.

- Even if you make a commit removing the secret from that file, that secret is still part of the history of commits (so, potentially, anyone can see that).





## Option 1

The best option is to change the code to use environment variables.
However, your secret will still be part of the history on github.

In this case, the easiest solution is to change the password/secret.




## Option 2

In some cases, you can not change that password/secret.
In those cases, `filter-branch` may be an option, since it allows you to rewrite the history (this has a lot of implications so it should be the last resort).


`$ git filter-branch --tree-filter 'rm -f ./path/to/passwords.txt' HEAD`

<!--
@note:
- this will re-write the entire history
- it may be worth to explore other options (e.g. re-writing history only from a specific commit where the error was made)
-->

Documentation: https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History#_removing_file_every_commit



NOTE:
- git filter-branch rewrites history


⚠️ WARNING ⚠️

> git filter-branch has a plethora of pitfalls that can produce non-obvious manglings of the intended history rewrite (and can leave you with little time to investigate such problems since it has such abysmal performance). 

> its use is not recommended. 


