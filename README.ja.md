# cron-surf-canary

[English](README.md) · [简体中文](README.zh-CN.md) · 日本語

[![on time](https://cron.surf/badge/keepryanl/cron-surf-canary/canary.yml.svg)](https://github.com/keepryanl/cron-surf-canary/actions/workflows/canary.yml)

[cron.surf](https://cron.surf/ja/github) の公開カナリアリポジトリです。GitHub Actions を定刻どおりに起動できているかを、そのまま見せるためのものです。

ワークフローは [`canary.yml`](.github/workflows/canary.yml) の 1 つだけです。`schedule:` トリガーはありません。それでも 5 分ごとに動くのは、cron.surf GitHub App が次のコメントを読み取り、時刻どおりに起動しているからです。

```yaml
on:
  workflow_dispatch:
  # cron.surf: */5 * * * *
```

各実行は開始時刻を出力します。本来の 5 分刻みの時刻と比べれば、どれだけ定刻に近いかがわかります。

**[Actions タブですべての実行を見る →](https://github.com/keepryanl/cron-surf-canary/actions/workflows/canary.yml)**

## 自分のリポジトリで使う

1. リポジトリに [cron.surf GitHub App](https://github.com/apps/cron-surf) をインストールします。
2. ワークフローに `workflow_dispatch:` を追加し、その下に `# cron.surf: <cron> [タイムゾーン]` のコメントを書きます。例: `# cron.surf: 0 9 * * * America/Los_Angeles`
3. デフォルトブランチにプッシュします。コミットの "cron.surf" チェックに次回以降の実行時刻が表示されます。

詳しくは [cron.surf/ja/github](https://cron.surf/ja/github) へ。
