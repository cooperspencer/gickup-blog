---
Title: Github
weight: 34
---

```yaml
  github:
    - token: some-token
      token_file: token.txt
      visibility:
        repositories: private
```
- `token`: your github token.
- `token_file`: alternatively, specify the token in a file, relative to current working directory when executed.
- `visibility`: set the visibility of created organizations and repositories
    - `repositories`: can be `private` or `public`, default is `private`