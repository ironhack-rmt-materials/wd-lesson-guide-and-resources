
# w7d4

<!-- 

Status: draft

Notes:
- Heavy concepts today (esp. lifecycle, useEffect, API calls, etc).
- On top of that, students are usually tired (yesterday's lab is demanding)
- Students that don't have solid concepts may find it challenging today

@todo:
- improve planning for this session
- improve examples (esp. for Routing)
- provide cheatsheet / summary (too many concepts, students struggle)

-->


## Quick lab review

Ask students for yesterday's LAB (specific questions)


## Refresh



## Today

Codealong Options:

- option 1: characters API.
  - sample repo: https://github.com/Ironborn-Ironhack-March-2022/react-characters-app

- option 2: add that functionality to "popcorn time" (movie characters + routing)



Codealong functionality (draft):
- (lifecycle and hooks) get & display list of characters from `https://ih-crud-api.herokuapp.com/characters`
- (routing): one page for the list of characters
- (routing): one page for each character (with static links and then with URL parameters)
  - note1: for that, create a component `<CharacterDetails>` and send a request to get the details of one character from the API (same pattern that they're asked to do in the LAB)
  - note2: display the nav menu in all pages (same pattern as today's lab) (or explain the two options: all pages vs. homepage only)
- extra: pass the list of characters to Header & render a dynamic menu in the Header