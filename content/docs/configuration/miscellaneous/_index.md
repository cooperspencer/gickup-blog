---
Title: Miscellaneous
weight: 40
---

There are additional options to set.
```yaml
cron: 0 22 * * *

log:
  timeformat: 2006-01-02 15:04:05
  file-logging:
    dir: log
    file: gickup.log
    maxage: 7

metrics:
  prometheus:
    endpoint: /metrics
    listen_addr: ":6178"
  heartbeat:
    urls:
      - http(s)://url-to-make-request-to
      - http(s)://another-url-to-make-request-to
```
- `cron`: you can add a cron expression to run gickup more than once. You can create and test the expression on https://crontab.guru/.
{{< tip >}}
If gickup runs in Docker, you might want to set the timezone for your container.
{{< /tip >}}
- `log`: this is everything related to logging.
    - `timeformat`: set it to a different time format for logging. The basics for time formats can be found at https://yourbasic.org/golang/format-parse-string-time-date-example/. This can also be set as an environment variable with `GICKUP_TIME_FORMAT`.
    - `file-logging`: logs can also be stored in a file.
        - `dir`: where to store your log.
        - `file`: in which file to store your log.
        - `maxage`: automatically cleanup files older than X days.
- `metrics`: everything related to metrics.
    - `prometheus`: enable prometheus metrics.
        - `endpoint`: by default it is `/metrics`, but set it to whatever you prefer.
        - `listen_addr`: by default it listens on `:6178`.
    - `heartbeat`: send `GET` requests to monitoring services like https://healthchecks.io/ or https://deadmanssnitch.com/.
        - `urls`: list of urls.