---
Title: Gitlab
weight: 16
---

```yaml
  gitlab:
    - token: some-token
      token_file: token.txt
      url: http(s)://url-to-gitlab
      user: some-user
      username: your-user
      password: your-password
      ssh: true
      sshkey: /path/to/key
      exclude: # this excludes the repos "foo" and "bar"
        - foo
        - bar
      include: # this includes the repo "foobar"
        - foobar
      excludeorgs: # this excludes repos from the organizations "foo" and "bar"
        - foo
        - bar
      includeorgs: # this includes repos from the organizations "foo1" and "bar1"
        - foo1
        - bar1
      wiki: true
      filter:
        lastactivity: 1y
        stars: 100
        excludearchived: true
        languages:
          - go
          - whatever
```

- `token`: your gitlab token. You don't need one, if you backup only public repositories.
- `token_file`: alternatively, specify the token in a file, relative to current working directory when executed.
- `url`: if empty, https://gitlab.com is used.
- `user`: the user you want to clone the repositories from.
{{< tip >}}
if you want to get everything from your user, leave out the `user` parameter and just use the token.
{{< /tip >}}
{{< tip "warning" >}}
for the clone process, either use:
 - username + password
 - sshkey
 - token
 - nothing, if you only clone public repositories
{{< /tip >}}
- `username`: user that will be used for the clone process.
- `password`: password for said user.
- `ssh`: boolean value if the clone should be done via ssh.
- `sshkey`: if empty, it uses your home directories' .ssh/id_rsa.
- `exclude`: you can exclude repositories.
- `include`: only clone those specific repositories.
- `excludeorgs`: leave out specific organizations of the user.
- `includeorgs`: only clone those specific organizations repositories.
- `wiki`: also clone the wikis of the repositories.
- `starred`: also clone the starred repositories of the `user`.
- `filter`:
  - `lastactivity`: only repos that were active in this time frame are cloned (y, M, d, h, m, s)
  - `stars`: clone repos with at least x stars.
  - `excludearchived`: do not clone archived repos.
  - `languages`: only clone repos of said languages.