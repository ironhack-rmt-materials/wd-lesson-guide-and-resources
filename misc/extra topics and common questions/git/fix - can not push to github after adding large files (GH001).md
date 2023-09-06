

# fix - can not push to github after adding large files (GH001)



## Issue 

Trying to push to Github, you get this error:

> GH001: Large files detected. You may want to try Git Large File Storage.


## Explanation

- GitHub's file size limit of 100.00 MB
- Even if you delete the files, they'll be part of your commit history


## Solution

This usally works: `git filter-branch -f --index-filter 'git rm --cached --ignore-unmatch filename'`

Source: https://stackoverflow.com/a/68569889/11298742


NOTE:
- git filter-branch rewrites history


⚠️ WARNING ⚠️

> git filter-branch has a plethora of pitfalls that can produce non-obvious manglings of the intended history rewrite (and can leave you with little time to investigate such problems since it has such abysmal performance). 

> its use is not recommended. 


