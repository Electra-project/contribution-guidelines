---
title: Commit Messages
category: Git
order: 2
---

Your commit messages MUST follow on of these two templates:

- `[workspace/path/to/file]: [infinitive verb] [target] (in [scope])`
- `[scope]: [infinitive verb] [target] (in [scope])`

**Rules**

- If you use the file workspace path, and this path includes `src`, you MUST omit the `src` part in the path.
- If you use the file workspace path, the file extension MUST be omitted.

**Examples**

```
> git status
Changes to be committed:
  modified:   src/libs/example.js
> git commit -m "libs/example: fix foo value in bar() method"
