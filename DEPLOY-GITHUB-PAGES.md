# GitHub Pages 公開手順

`株式会社HOWL` のサイトを `GitHub Pages` と `ムームードメイン` で公開するためのメモです。

## 1. GitHub にアップロード

このフォルダの中身を GitHub リポジトリにアップロードします。

例:

- リポジトリ名: `howl-site`
- ブランチ: `main`

## 2. GitHub Pages を有効化

1. GitHub の対象リポジトリを開く
2. `Settings > Pages` を開く
3. `Build and deployment` で `Deploy from a branch` を選択
4. `Branch` は `main`、フォルダは `/ (root)` を選択
5. 保存する

数分待つと、いったん GitHub 側のURLで公開されます。

## 3. 独自ドメインを設定

GitHub の `Settings > Pages > Custom domain` に `hhhowl.com` を入力します。

今回は `hhhowl.com` をそのまま使う前提です。

## 4. ムームードメイン側のDNS設定

### ルートドメインを GitHub Pages に向ける場合

ムームードメインで `hhhowl.com` の `A` レコードを次の4つに設定します。

- `185.199.108.153`
- `185.199.109.153`
- `185.199.110.153`
- `185.199.111.153`

### `www` を GitHub Pages に向ける場合

`CNAME` レコードを設定します。

- ホスト名: `www`
- 値: `<GitHubユーザー名>.github.io`

例:

- GitHub ユーザー名が `koshiro` なら `www -> koshiro.github.io`

今回は必須ではありません。まずは `hhhowl.com` だけ公開すれば十分です。

## 5. メール設定の注意

すでに独自メールを使っている場合、`MX` レコードは削除しないでください。

通常は次だけ触れば大丈夫です。

- Webサイト用: `A` または `CNAME`
- メール用: 既存の `MX`

`MX` を消さなければ、メールとWebサイトは同じドメインで共存できます。

## 6. CNAME ファイル

独自ドメインを固定するため、このフォルダには `CNAME` ファイルを同梱しています。
中身は 1 行だけです。

例:

```txt
hhhowl.com
```

`www` で運用するなら:

```txt
www.hhhowl.com
```

現在の設定値:

```txt
hhhowl.com
```

## 7. HTTPS

GitHub Pages 側でドメイン認識後、`Enforce HTTPS` を有効にします。

DNS反映には少し時間がかかることがあります。
