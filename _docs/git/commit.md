---
title: Commit
category: Git
order: 1
---

Each of your commit MUST follow these 2 rules:
- Any commit should be working by itself in order to allow a rollback to this commit without breaking the project.
- A commit should be focused and concerns a few (ideally just one) files in order to ease the peer-review process and the log history checking.

Some exceptional cases can skip this rule:
- Design integration (CSS, etc)
- Refactoring

However, in these cases, they should be done in a decicated pull request and do not integrate any other kind of change.
