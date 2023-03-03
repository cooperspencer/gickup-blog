---
Title: Any
weight: 20
---

```yaml
  any:
    - token: some-token
      token_file: token.txt
      url: url-to-any-repo 
      username: your-user 
      password: your-password
      ssh: true 
      sshkey: /path/to/key
    - url: can-also-be-a-local-path-to-a-bare-repo
```
- `token`: Token of the hoster. It can also be an environment variable.
- `token_file`: alternatively, specify the token in a file, relative to current working directory when executed.
- `url`: can be https, http or ssh. Could also be a local bare repository
- `username`: user that will be used for the clone process.
- `password`: password for said user.
- `ssh`: boolean value if the clone should be done via ssh.
- `sshkey`: if empty, it uses your home directories' .ssh/id_rsa.