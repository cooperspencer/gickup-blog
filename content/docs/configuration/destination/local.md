---
Title: Local
weight: 34
---

```yaml
  local:
    - path: /some/path/gickup
      structured: true
      zip: true
      keep: 5
      bare: true
```
- `path`: path to store your backup
{{< tip >}}
If you use Docker, don't forget to mount the path of your backup!
{{< /tip >}}
- `structured`: if set to `true`, it checks out the repos in a more structured way, like `hoster/user|organization/repository`
- `zip`: zips the repository
- `keep`: keeps x latest backups
- `bare`: clones it as bare