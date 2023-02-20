---
Title: Bitbucket
weight: 17
---

```yaml
  bitbucket:
    - url: http(s)://url-to-bitbucket
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
      filter:
        lastactivity: 1y
```
- `url`: if empty, https://bitbucket.org is used.
- `user`: the user you want to clone the repositories from.
{{< tip >}}
if you want to get everything from your user, leave out the `user` parameter and just use the token.
{{< /tip >}}
{{< tip "warning" >}}
for the clone process, either use:
 - username + password
 - sshkey
 - nothing, if you only clone public repositories
{{< /tip >}}
- `username`: user that will be used for the clone process.
- `password`: password for said user.
- `ssh`: boolean value if the clone should be done via ssh.
- `sshkey`: if empty, it uses your home directories' .ssh/id_rsa.
- `exclude`: you can exclude repositories.
- `include`: only clone those specific repositories.
- `filter`:
  - `lastactivity`: only repos that were active in this time frame are cloned (y, M, d, h, m, s)