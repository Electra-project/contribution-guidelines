---
title: Commit Messages
category: Git
order: 2
---

A commit message is templated either like this:

- `[PATH]: [ACTION] [TARGET] (in [SCOPE])`

or like that:

- `[SCOPE]: [ACTION [TARGET]`

The first one will generally be prefered over the second one since the second is more specific to edge cases.

---

## Rules

- The `PATH` MUST be the workspace relative file or directory path WITHOUT any trimming slash.
- The `PATH` and `ACTION` MUST be in lowercase.
- If the `PATH` starts with `src/`, you MUST omit the `src/` part.
- The `PATH` MUST omit the file extension.
- If the `PATH` is an unnamed file (.env, .travis.yml), you MUST use the `[SCOPE]: ...` template.
- The `ACTION` MUST be an infinitive verb.

---

## Common Actions

- `add`: When you added a new behavior to the code, a new dependency or a new config property.
- `comment`: When you added, removed or updated the comments. It's not required to add a target in this case.
- `create`: When you create a new file. You must use this one only file by file.
- `delete`: When you delete a file or a directory. It's not required to add a target in this case.
- `fix`: When you fixed a bug or a glitch. If this fix concerns a commit that you did previously on this branch, squash it instead or creating an endless list of "self-fixes".
- `lint`: When you change the code source presentation or fix linter errors. This does **not** include renaming of variables, which is considered as a refactoring.
- `migrate`: When you change the code source presentation or fix linter errors. This does **not** include renaming of variables, which is considered as a refactoring.
- `move`: When you move a file to another workspace path. You can also rename it if nexessary within the same commit.
- `rename`: When you rename a file BUT do ot change its workspace path.
- `update`: When you update a text, a markdown or a test file. It's not required to add a target in this case.
- `upgrade`: When you upgrade dependencies.

---

## Common Scopes

- `.editorconfig*`: `editorconfig: `
- `.env*`: `env: `
- `.travis*`: `travis: `
- `package*`: `npm: `
- `webpack*.config*`: `webpack: `

---

## Examples

```bash
> git status
Changes to be committed:
  modified:   src/libs/example.js
> git commit -m "libs/example: fix foo value in bar() method"
```

```bash
> git status
Changes to be committed:
  modified:   src/libs/example.spec.js
> git commit -m "libs/example: update tests"
```

```bash
> npm upgrade
[...]
> git add package*
> git status
Changes to be committed:
  modified:   src/libs/package-lock.json
  modified:   src/libs/package.json
> git commit -m "npm: upgrade dependencyies"
```
