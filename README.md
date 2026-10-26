# cron-surf-canary

English · [简体中文](README.zh-CN.md) · [日本語](README.ja.md)

[![on time](https://cron.surf/badge/keepryanl/cron-surf-canary/canary.yml.svg)](https://github.com/keepryanl/cron-surf-canary/actions/workflows/canary.yml)

A public canary for [cron.surf](https://cron.surf/en/github) on-time triggers for GitHub Actions.

This repository has one workflow, [`canary.yml`](.github/workflows/canary.yml). It has no `schedule:` trigger. It runs every five minutes because the cron.surf GitHub App reads one comment and dispatches it on time:

```yaml
on:
  workflow_dispatch:
  # cron.surf: */5 * * * *
```

Each run prints when it started. Compare that with the five-minute mark it was due at to see how close to on time the dispatch was.

**[See every run in the Actions tab →](https://github.com/keepryanl/cron-surf-canary/actions/workflows/canary.yml)**

## Use it in your own repository

1. Install the [cron.surf GitHub App](https://github.com/apps/cron-surf) on the repository.
2. Add `workflow_dispatch:` to the workflow and put a `# cron.surf: <cron> [time zone]` comment under it, for example `# cron.surf: 0 9 * * * America/Los_Angeles`.
3. Push to the default branch. A "cron.surf" check on the commit lists the next runs.

More at [cron.surf/en/github](https://cron.surf/en/github).
