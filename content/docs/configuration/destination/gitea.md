---
Title: Gitea
weight: 31
---

```yaml
  gitea:
    - token: some-token
      token_file: token.txt
      user: some-name
      url: http(s)://url-to-gitea
      createorg: true
      lfs: true
      mirror:
        mirrorinterval: 8h
        enabled: false
      visibility:
        repositories: private
        organizations: private
```
- `token`: your gitea token.
- `token_file`: alternatively, specify the token in a file, relative to current working directory when executed.
- `url`: if empty, https://gitea.com is used.
- `user`: the user/org you want to mirror the repositories to. 
- `createorg`: if activated, it will create the value in user as organization if it doesn't exist on the system.
- `lfs`: enable lfs on the mirror repository.
{{< tip >}}
if `user` is empty and `createorg` is set to `true`, it creates organizations based on the original author.
{{< /tip >}}
- `mirror`: handle the mirror functionality
  - `mirrorinterval`: resync interval for gitea. It only works if `enabled` is set to `false`.
  - `enabled`: if set to `false` gitea will handle the mirror process itself, if set to `true` gickup will clone the repo locally and push it to gitea.
  {{< tip >}}
  especially useful for [codeberg](https://codeberg.org) because they disabled the mirror feature.
  {{< /tip >}}
- `visibility`: set the visibility of created organizations and repositories
    - `repositories`: can be `private` or `public`, default is `private`
    - `organizations`: can be `private`, `limited` or `public`, default is `private`