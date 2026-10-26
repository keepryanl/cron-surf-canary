# cron-surf-canary

[English](README.md) · 简体中文 · [日本語](README.ja.md)

[![on time](https://cron.surf/badge/keepryanl/cron-surf-canary/canary.yml.svg)](https://github.com/keepryanl/cron-surf-canary/actions/workflows/canary.yml)

这是 [cron.surf](https://cron.surf/zh/github) 的公开金丝雀仓库，用来展示 GitHub Actions 准点运行的实际效果。

仓库里只有一个工作流 [`canary.yml`](.github/workflows/canary.yml)。它没有 `schedule:` 触发，之所以每 5 分钟运行一次，是因为 cron.surf GitHub App 读取了下面这行注释，并按时启动它：

```yaml
on:
  workflow_dispatch:
  # cron.surf: */5 * * * *
```

每次运行都会打印开始时间。拿它和应当运行的那个 5 分钟整点比一比，就能看出启动得有多准时。

**[在 Actions 页查看每一次运行 →](https://github.com/keepryanl/cron-surf-canary/actions/workflows/canary.yml)**

## 在你自己的仓库里使用

1. 在仓库上安装 [cron.surf GitHub App](https://github.com/apps/cron-surf)。
2. 在工作流里加上 `workflow_dispatch:`，并在下面写一行 `# cron.surf: <cron> [时区]` 注释，例如 `# cron.surf: 0 9 * * * America/Los_Angeles`。
3. 推送到默认分支。提交上的 "cron.surf" 检查会列出接下来几次运行时间。

详见 [cron.surf/zh/github](https://cron.surf/zh/github)。
