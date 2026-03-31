# HOWL Site Template

`GitHub Pages` と `Cloudflare Pages` のどちらでもそのまま公開できる、
`株式会社HOWL` の会社概要 + プライバシーポリシー用最小構成テンプレートです。

## ファイル構成

- `index.html`: 会社概要
- `privacy.html`: プライバシーポリシー
- `styles.css`: 共通スタイル

## 使い方

1. 必要に応じて文言や見た目を調整する
2. 独自ドメインを使う場合は `DEPLOY-GITHUB-PAGES.md` を参照する
3. `CNAME` は `hhhowl.com` で作成済み

## GitHub Pages

1. このフォルダを GitHub リポジトリにアップロード
2. GitHub の `Settings > Pages` を開く
3. `Deploy from a branch` を選び、公開したいブランチの `/ (root)` を指定
4. 独自ドメインを使う場合は `Custom domain` にドメインを設定
5. 詳細は `DEPLOY-GITHUB-PAGES.md` を参照

## Cloudflare Pages

1. GitHub リポジトリを Cloudflare Pages に接続
2. Framework preset は `None`
3. Build command は空欄
4. Output directory は `/`
5. 独自ドメインを接続

## 補足

- 完全な静的サイトなのでサーバー処理は不要です
- 独自メールを使っている場合は、DNS で `MX` レコードを消さないように注意してください
