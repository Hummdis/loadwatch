---
title: Development
date: 2021-09-18 13:42
tags:
---

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
