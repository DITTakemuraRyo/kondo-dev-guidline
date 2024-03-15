---
title: "はじめに"
---
# Reactとは
Facebookによって開発されたJavascriptのライブラリです。
**コンポーネント**と呼ばれる部品を使ってページやアプリの画面を組み立てていく。
:::message
React におけるコンポーネントとは、マークアップを返す JavaScript 関数のこと。
このマークアップはJSXといって、JavaScriptファイル内にHTMLのようなコードを記述できる
初めは意味わからないけどそーゆーもの程度で理解
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

