---
title: Commit
category: Git
order: 1
---

---

## Rules

- Any commit MUST be working by itself in order to allow a rollback to this commit without breaking the project.
- A commit MUST be focused and concerns a few (ideally just one) files in order to ease the peer-review process and the log history checking.

---

## Exceptions

Some edge cases can skip this rule:

- Design integration (CSS, etc)
- Migration of the code to integrate a major upgrade from a dependency (Typescript, Webpack, etc)
- Refactoring

However, in these cases, they should be done in a decicated pull request and do not integrate any other kind of change.
