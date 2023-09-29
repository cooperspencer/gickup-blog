---
Title: Onedev
weight: 35
---

```yaml
  onedev:
    - token: some-token
      token_file: token.txt
      url: http(s)://url-to-onedev
      organization: myorg
      force: true
```
- `token`: your onedev token.
- `token_file`: alternatively, specify the token in a file, relative to current working directory when executed.
- `url`: if empty, https://code.onedev.io is used.
- `organization`: name of the parent repository you want to backup to.
- `force`: enable force push.