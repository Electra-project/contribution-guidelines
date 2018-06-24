---
title: Edit Commits
category: Git
order: 3
---

You made a mistake ? That's fine since the magic of Git allow you to rectify almost any mistake you made. Here is how to do it.

## Updating the last commit message

```bash
git commit --amend
```

You may need to force the push after that if you did already pushed the edited commit:

```bash
git push origin head -f
```

## Squashing commits

Squashing commits allow you to "merge" multiple commits that shluld be gathered in order to keep the commits history as clean as possible.

Here is an example that applies:

```
> git log
commit e3bbca59f743e9dc78f0608042b1cf4365fbcaeb (HEAD -> master, origin/master)
Author: Ivan Gabriele <ivan.gabriele@gmail.com>
Date:   Sun Jun 24 13:16:51 2018 +0200

    libs/anotherExample: add doThis() method

commit 398a7e41002f0c30e8baf463f824729cb0c21032
Author: Ivan Gabriele <ivan.gabriele@gmail.com>
Date:   Sun Jun 24 13:15:25 2018 +0200

    libs/example: fix typo again in foo value

commit 65f2a18775670f1f29cccc6f14474fcf9744f20f
Author: Ivan Gabriele <ivan.gabriele@gmail.com>
Date:   Sun Jun 24 13:11:38 2018 +0200

    libs/example: fix typo in foo value

commit 0896f05330bf3e3203723485d6ab97fec870c379
Author: Ivan Gabriele <ivan.gabriele@gmail.com>
Date:   Sun Jun 24 12:57:59 2018 +0200

    libs/example: fix foo value in bar() method
```

Obviously I want to merge the second, the third and fourth commits together. For that I just need to do what is call an "interactive rebase" on my last 4 commits:

```bash
> git rebase -i HEAD~4
```

```bash
pick 0896f05 libs/example: fix foo value in bar() method
pick 65f2a18 libs/example: fix typo in foo value
pick 398a7e4 libs/example: fix typo again in foo value
pick e3bbca5 libs/anotherExample: add doThis() method
```

Now I can use `s` to squash my commits by editing the file like that:

```bash
pick 0896f05 libs/example: fix foo value in bar() method
s 65f2a18 libs/example: fix typo in foo value
s 398a7e4 libs/example: fix typo again in foo value
pick e3bbca5 libs/anotherExample: add doThis() method
```

I save the file and the text editor will re-open to suggest me to edit the commit message of these 3 merged commits. Be careful, by default, it will propose all the commit messages together:

```bash
# This is a combination of 3 commits.
# This is the 1st commit message:

libs/example: fix foo value in bar() method

# This is the commit message #2:

libs/example: fix typo in foo value

# This is the commit message #3:

fix typo again in foo value
```

We obviously don't want that, so let's remove the other useless messages. Under Vim use the `dd` shortcut to delete a line. You can leave the remaining comments, they will be ignored anyway.

```
# This is a combination of 3 commits.
# This is the 1st commit message:

libs/example: fix foo value in bar() method

# This is the commit message #2:


# This is the commit message #3:
```

We can now save the file (with `:` then `wq` under Vim) and push our changes.

You may need to force the push after that if you did already pushed the edited commit:

```bash
git push origin head -f
```
