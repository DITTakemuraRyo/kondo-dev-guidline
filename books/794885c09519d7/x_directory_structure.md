---
title: "ディレクトリ構成"
---
# ディレクトリ構成
共通的な機能と各ページに依存した機能がごっちゃまぜになると後々苦しむので、以下ディレクトリ構成とする。

```
.
└── src
    ├── components # 共通コンポーネント
    ├── configs # ライブラリの設定等
    ├── features # 機能に関連するコンポーネント
    │   ├── Dashboard
    │   │   ├── Chart.js
    │   │   ├── Dashboard.js
    │   │   ├── Deposits.js
    │   │   ├── Orders.js
    │   │   ├── Title.js
    │   │   └── listItems.js
    │   ├── SignIn
    │   │   └── sign-in.js
    │   └── SignUp
    │       └── sign-up.js
    ├── hooks # 共通フック
    ├── pages #URLに対応するコンポーネント(1ページ、1index.js)
    │   ├── DashboardPage
    │   │   └── index.js
    │   ├── SignInPage
    │   │   └── index.js
    │   └── SignUpPage
    │       └── index.js
    ├── index.js
    ├── routes.js
    └── setupTests.js
```
下記サイトのディレクトリ構成を参考にしている。
https://hello.shelfy.co.jp/76c13c6e85564653b335ec954d17da09

以下各ディレクトリの説明
### pages
URLに対応する大枠のコンポーネントを配置する。
**ディレクトリ名はXXPageで統一する。**
ディレクトリの中はindex.jsのみ。
このindex.jsは各ページの全体像が分かるようにする。
ロジックなどの細かい処理はここでは実装しないで極力シンプルに。
### features
各機能に依存するComponentやHookなどのファイルを配置する。
ここのコンポーネントをpagesからimportするイメージ。
それぞれの機能名でディレクトリを切って、各ファイルを置く。
:::message
各機能のディレクトリはパスカルケースにする。
:::
### components
機能に依存しない共通的なComponentを配置する。
ヘッダーや共通のボタンとか。
### hooks
機能に依存しない共通的なHookを配置する。
axiosのカスタムフックとか。
### configs
ライブラリの設定とかを配置する。

## 各ディレクトリファイルの依存関係
⇒の向きに依存する。
pages ⇒ features・components ⇒ hooks
:::message
共通的な機能（components・hooks）が各機能に依存したfeaturesをimportしないように！
:::







