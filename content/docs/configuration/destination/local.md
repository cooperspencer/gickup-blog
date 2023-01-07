---
Title: Local
weight: 34
---

```yaml
  local:
    - path: /some/path/gickup
      structured: true
      date: true
      zip: true
      keep: 5
```
- `path`: path to store your backup
{{< tip >}}
If you use Docker, don't forget to mount the path of your backup!
{{< /tip >}}
- `structured`: if set to `true`, it checks out the repos in a more structured way, like `hoster/user|organization/repository`
- `date`: creates a path structure based on the day, e.g.: `~/backup/2023/01/07/`
- `zip`: zips the repository
- `keep`: keeps x latest backups