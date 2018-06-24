---
title: Commit Messages
category: Git
order: 2
---

A commit message is templated like this:

- `[PATH]: [ACTION] [TARGET] (in [SCOPE])`

or:

`[SCOPE]: [ACTION[] [TARGET]`

**Rules**

- The **PATH** MUST be the workspace relative file or directory path WITHOUT any trimming slash.
- The **PATH** and **ACTION** MUST be in lowercase.
- If the **PATH** starts with `src/`, you MUST omit the `src/` part.
- The **PATH** MUST omit the file extension.
- If the **PATH** is an unnamed file (.env, .travis.yml), you must use the `[SCOPE]: ...` template.

**Commonly Used Scopes**

- `.editorconfig*`: `editorconfig: `
- `.env*`: `env: `
- `.travis*`: `travis: `
- `package*`: `npm: `

**Examples**

```bash
> git status
Changes to be committed:
  modified:   src/libs/example.js
> git commit -m "libs/example: fix foo value in bar() method"
```
