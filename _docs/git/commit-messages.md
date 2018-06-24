---
title: Commit Messages
category: Git
order: 2
---

A commit message is templated either like this:

- `[PATH]: [ACTION] [TARGET] (in [SCOPE])`

or like that:

- `[SCOPE]: [ACTION[] [TARGET]`

The first one will generally be prefered over the second one since the second is more specific to edge cases.

### Rules

- The **PATH** MUST be the workspace relative file or directory path WITHOUT any trimming slash.
- The **PATH** and **ACTION** MUST be in lowercase.
- If the **PATH** starts with `src/`, you MUST omit the `src/` part.
- The **PATH** MUST omit the file extension.
- If the **PATH** is an unnamed file (.env, .travis.yml), you must use the `[SCOPE]: ...` template.

### Common Patterns

- `.editorconfig*`: `editorconfig: `
- `.env*`: `env: `
- `.travis*`: `travis: `
- `package*`: `npm: `

### Examples

```bash
> git status
Changes to be committed:
  modified:   src/libs/example.js
> git commit -m "libs/example: fix foo value in bar() method"
```
