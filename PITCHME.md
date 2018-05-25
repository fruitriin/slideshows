# Vue.js ハンズオン!
## 付録 - 初学者へ贈るコツ
果物リン@FruitRiin
<div class="date"> 2018/05/25 - nakameguro.php #03</div>


---

### \#nakameguro_php

---

## ES6入門
- 今までjQueryしか触ったことがない？
- つ [ES2015\(ES6\) 入門 \- Qiita](https://qiita.com/soarflat/items/b251caf9cb59b72beb9b)

---

## 小さく始める

- 要らないライブラリは入れない
  - vue-routerもvuexも最初は入れない！
- コンポーネントも分割しない
- まず雰囲気をつかむ！

--- 

## 大きくする
- 別のプロジェクトをvue-cliで参考にする
 - コンポーネントの分割にトライ！
 - vue-routerを入れてプロジェクトを見比べる
 - vuexも同様に（一度にやらない）

---
## 省略記法

- v-bind:property = :property
 - :value とか
 - :style はオブジェクトを渡してもOK
- v-on:click = @click
 - v-on のショートハンドが@

---
## v- と文字列

- v-bind, v-on etc... はJS式としてパース
 - 文字列は 'シングルクォート' でくくる
```
<ul>
 <li v-bind:class="'type-' + n" v-for="n in list">{{n}}</li>
</ul>
```

---?image=bg/navy.png

## 意外な罠
- dataは関数にしなければならない
- **dataをアロー関数にしてはならない**
  - スコープがすっぽ抜けて悩みます 😇
- methods, computed etc も同様

---

## コンポーネントの設計
### Atomicデザインがよさそう
- [Atomic Design を分かったつもりになる \| DeNA DESIGN BLOG](http://design.dena.com/design/atomic-design-%E3%82%92%E5%88%86%E3%81%8B%E3%81%A3%E3%81%9F%E3%81%A4%E3%82%82%E3%82%8A%E3%81%AB%E3%81%AA%E3%82%8B/)
- [Vue\.js からみた AtomicDesign – Takanori Sugawara – Medium](https://medium.com/@t_sugawara/vue-js-%E3%81%8B%E3%82%89%E3%81%BF%E3%81%9F-atomicdesign-e90517842801)

---

## モジュールの紹介

- あとからモジュールを追加して機能が増える！
- 独断と偏見で定番のやつとかピックアップ

---
### vue-router

- Vue.jsにルーティング機能を提供
 - 公式ライブラリ！
- 「URLで表示を切り替えたい！」
- URLとパラメータをハンドリング
- 変数 ←→ URL

--- 

### Vuex

- Flexのデータストア
- コンポーネント間でデータをやりとり
- Vueのために作られているのでReduxより簡単
- TypeScript？知らない子ですね……
 - 補完の効き具合がいまいちらしい
---

### Nuxt.js

- Vue.js でSSRするためのフレームワーク
- 色々なモジュール全部入りでレールに乗る
- 今めちゃくちゃアツいらしい
- インストールはvue-cliから

 ```
 vue init nuxt-community/starter-template <project-name>
 ```

---
## UIコンポーネント

- パーツ単位で「コンポーネント化」できる
- 「コンポーネントを共有しようぜ」「それだ」


---
### Element UI

- 定番のUIコンポーネント集
- 高機能で使いやすい！
 - レイアウト、メニュー
 - ボタン、フォーム、スイッチ、スライダー
 - タイムピッカー、カレンダー
 - アップローダー

などなど。 26k stars 

---

### BootstrapVue

- Bootstrap 4をVueで！
 - Bootstrapにあるコンポーネントをリメイク
 - ちゃんとVueのコンポーネント
 - 実はjQueryに依存してない！
 
 5k stars 

---

## 既存のサイトにVue.jsを導入

---

### インラインでも使える

```
<head>
  <!-- 本番バージョン、サイズと速度のために最適化されています -->
  <script src="https://cdn.jsdelivr.net/npm/vue"></script>
</head>
<body>
<div id="app">
  {{ message }}
</div>
<!-- エントリポイントのあとに読み込む -->
<script src="app.js"></script>
```

---

### app.js サンプル

```
var app = new Vue({
  el : "#app",
  data: {
    message: 'Hello Vue!'
  }
})

```
#app 内のDOMに書かれたVueSyntaxが展開される


---

### テンプレートもOK

```
var app = new Vue({
  el : "#app",
  data: {
    message: 'Hello Vue!'
  },
  template: `
    <p>template say {{ message }}</p>
  `
})
```

コンポーネントもOK


---

### 制限
- ES6が使えないとつらい
 - テンプレートにテンプレートリテラルほしい
 - 配列操作やajaxとかにアロー関数使いたい
- Scoped CSSは？
 - そんなものはない
- Webpackもない
 - ちょっとパッケージを入れてとかできない
- HMRとかもない

---
### 制限2
- JSでDOMを直接書き換えると非常に危険
 - **Vueのライフサイクルに巻き込まれて吹き飛ぶ**

---
### 直接のDOM操作で壊れる

```
Virtual DOMの基本アプローチは仮想DOM -> 生のDOM変換であり、
この手続に依存する限り生DOMを触ることは推奨されません。
patchに巻き込まれると、知らないうちに
イベントハンドラごと吹き飛ぶ可能性があります。
しかも内部のアルゴリズムに依存するので非常にデバッグ困難です。
```

> [なぜ仮想DOMという概念が俺達の魂を震えさせるのか \- Qiita](https://qiita.com/mizchi/items/4d25bc26def1719d52e6) by mizuchi

---

### 結論＝できるよ！

あまりオススメしない

---

## LaravelでVue.js

- ステップバイステップな記事を書いた  
[LaravelからVue\.jsを使う最短レシピとTips \- Qiita](https://qiita.com/fruitriin/items/e0f2c9aa035c3ff2c874)
- 割りとチョロい
- LaravelはDBを扱うAPIを生やすといい感じ

---

## RailsでVue.js

- Rails Wayではない＝かなりつらいという噂
- APIサーバーとして使うなら問題なさそう
- Rails Webpackerとかあるけどつらそう
 - ついでにあまり旨味もなさそう

---

### サーバーに求められるもの

- もはやJSONを返せればなんでもいいらしい
- 今のご時世ブラウザはJS支配。

---

## npm packageのイケてるやつ

- Rodash - 関数型配列操作など
- moment.js - 時間関係のパーサ、コンバータ
- string.js - Stringクラスの強いやつ
- URI.js - URIやクエリストリングを扱う
- store.js - LocalStorageのwrapper

---
~~Rodashとmomentしかまだ使ったことがない~~

---

### Vue.jsはいいぞ 

---
# Thanks 
