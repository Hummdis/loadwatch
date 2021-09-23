<<<<<<< HEAD
---
title: Development
date: 2021-09-18 13:42
tags:
---

=======
>>>>>>> 5d5cf7a (todo notes)
# Development

How to clone repo for testing:

```bash
git clone --branch {branch-name} https://github.com/kraker/loadwatch.git /opt/loadwatch
cd /opt/loadwatch
chmod +x loadwatch
```

Optional oneliner that does the same thing:

```bash
git clone --branch memory-dev https://github.com/kraker/loadwatch.git /opt/loadwatch && chmod +x /opt/loadwatch/loadwatch
```

Run script manually with:

```bash
/opt/loadwatch/loadwatch
```
<<<<<<< HEAD
=======

## TODO

- [ ] Cleanup echo's into groupings with {} or whatever makes sense
- [ ] Here doc for `factor_check()` function
- [ ] Add a `bc_check()` function?
- [ ] Add a check for if current script is at newest version before running
      manual updates?
- [ ] Fix other ShellCheck things if there are any?
>>>>>>> 5d5cf7a (todo notes)
