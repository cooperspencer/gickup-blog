---
Title: Gitlab
weight: 33
---

```yaml
  gitlab:
    - token: some-token
      token_file: token.txt
      url: http(s)://url-to-gitlab
```
- `token`: your gitlab token. You don't need one, if you backup only public repositories.
- `token_file`: alternatively, specify the token in a file, relative to current working directory when executed.
- `url`: if empty, https://gitlab.com is used.
{{< tip "warning" >}}
A backup to Gitlab works in general. With the community edition, it just migrates the repository to Gitlab. Mirroring is only supported in the Enterprise Edition.
I have no access to an Enterprise Edition, therefore I can't test it properly.
{{< /tip >}}