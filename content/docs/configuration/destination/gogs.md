---
Title: Gogs
weight: 32
---

```yaml
  gogs:
    - token: some-token
      token_file: token.txt
      user: some-name
      url: http(s)://url-to-gogs
      createorg: true
      mirror:
        enabled: false
      visibility:
        repositories: private
```
- `token`: your gogs token.
- `token_file`: alternatively, specify the token in a file, relative to current working directory when executed.
- `url`: there is no default value.
- `user`: the user/org you want to mirror the repositories to. 
- `createorg`: if activated, it will create the value in user as organization if it doesn't exist on the system.
{{< tip >}}
if `user` is empty and `createorg` is set to `true`, it creates organizations based on the original author.
{{< /tip >}}
- `mirror`: handle the mirror functionality
  - `enabled`: if set to `false` gogs will handle the mirror process itself, if set to `true` gickup will clone the repo locally and push it to gogs.
- `visibility`: set the visibility of created repositories
    - `repositories`: can be `private` or `public`, default is `private`