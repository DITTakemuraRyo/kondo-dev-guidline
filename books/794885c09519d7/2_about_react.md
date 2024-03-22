---
title: "Reactとは"
---
# Reactとは
Reactはフレームワークではなく、Facebookによって開発されたWeb画面のUI構築に特化したJavascriptのライブラリです。
SPA（シングルページアプリケーション）の開発で特に人気があります。
:::message
SPAとはWebページを一度読み込んだら、ページ遷移することなく画面や見た目を切り替える仕組みのこと。
途中でページの読み込みが無いため、シームレスな遷移を実現できる。
:::
https://ja.react.dev/
# 特徴
## コンポーネント
**コンポーネント**と呼ばれる部品を使ってページやアプリの画面を組み立てていく。
コンポーネント = 画面に表示させるためのUIの部品。
いつでもコンポーネントを再利用できるのが強み。
:::message
React におけるコンポーネントとは、マークアップを返す JavaScript 関数のこと。
このマークアップはJSXといって、JavaScriptファイル内にHTMLのようなコードを記述できる。
:::
```js: button.js
export const MyButton = () => {
  return (
    <button>MyButton</button>
  );
}
```
```js: main.js
import { MyButton } from '../../commo/MyButton'; // コンポーネントをインポートする

export const MainPage = () => {
  return (
    <MyButton/>
  );
}
```
## 仮想DOM
実際のDOMとは別に仮想のDOMを構築して、変更前の仮想DOMとの差分だけをとって更新し、実際のDOMに反映することができる。
従来のDOMと比べページ表示を高速化できる。
仮想DOMとDOMについてはこちらのサイトで分かり易く記載されている。
https://qiita.com/seira/items/6767e222890c9890ecb9
## JSX
JavaScriptの構文拡張で、JavaScriptファイル内にHTMLのようなコードを記述できる。
実際はJavaScriptではないためブラウザでこのコードを実行することはできない。
HTMLにはない独自のルールがあるので公式を参照。
https://ja.react.dev/learn/writing-markup-with-jsx

# よくある疑問
## なぜわざわざNode.js上で開発するのか
>Node.jsはブラウザではなくサーバー上でJavaScrptを動かすために使われる。
>なぜブラウザ上で動かすReactアプリの開発に使われるのか。

パッケージの管理で便利！
複数のパッケージをアプリで利用したりすると、パッケージ同士の競合やバージョン管理の問題がある。
Node.jsにはnpmなどのパッケージ管理システムがあるため。



