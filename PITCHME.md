# あえて<br>PHPerにすすめる<br>Vue.js入門

<div class="auther">
株式会社ORATTA
中島 凜 (果物リン@FruitRiin)
</div>

<div class="date">PHPConference関西2018</div>

Note:
- 東京でエンジニアをしている
- きっかけPHPerKaigi2018でテンションが上がってCfPを申し込んだ
- PHPカンファレンス関西という場に立てて光栄である
---

## 自己紹介

icon.png

- 株式会社ORATTA 
 - ソシャゲの開発運営
 - サーバーアプリケーションエンジニア
- 趣味JSer
 - Vue.jsはいいぞ！


---

## 株式会社ORATTA

oratta.png

戦国アスカZEROとか作ってます。  
PWA版『クイック』をリリースしました！(2018.6)

Note:
お勤めなのでちょっと自社の紹介させてください。
---

## 戦国アスカZERO

Asuka.png

なでなでするほど強くなるRPG
App Store, Google Play, Chrome, Yahoo! Mobagee


---
## 全国CM打ちました(2017.8)

CM.png

この顔にピンときたらORATTAです。

---
## ORATTAの社内マスコット

lydia.png

この顔にピンときたらORATTAです  
（最初にリリースしたゲームのナビキャラです）

Note:
社内のSlack botなどでめっちゃ活躍してますが、
一般にはほとんど見かけることはないかと思います

---
## Next Project is Laravel

laravel.png

このロゴにピンときたらORATTAです？

Note:
このロゴとゲーム作りのキーワードにピンときたらORATTAです！

---
## We are Hireling

orattalogo.png

このロゴにピンときたらORATTAです。
Note:
会社のロゴです。
東京の会社ですが、ゲームづくりに興味がある人は会社のホームページも見てみてください。

これは余談なんですが、私が採用されたきっかけはPHP BLTっていうイベントでうちのリーダーと意気投合しまして、
「会社の採用ページの申し込みフォームの備考に僕の名前書いて」ってリーダーに言われてたので
次の日申し込んだらわりとスルッと入ったみたいなエピソードがあります。

ちょうど拡大の時期なので、ゲームが好きなら積極的に採用するよって言ってましたよ！


---

<div class="attention font-big">
はい。
</div>
Note:
会社紹介おわり。お勤め終了でございます。


---
# あえて<br>PHPerにすすめる<br>Vue.js入門


Note:
戻ってきました。

---
## お品書き
- 最初のPHP経験を思い出して
- なぜ「Vue.js」なのか
- Vueの始め方 Laravel編
- Vue.js Syntax ライブコーディング
- 初学者へ送る4つのヒント
- My Fails of the Vue


---

# 最初のPHP経験は？

---

## 初めてのPHP経験は？
- 初めてPHPに触れた頃を思い出してみてください
 - PHPといえばテンプレートエンジンだった
  - echo "&lt;html&gt;"; 😇
 - smarty とかでHTMLを書く
 - JSは片手間に書くもの

とにかく我々もUXを提供していた！

---

<div class="attention font-big">
few years later...
</div>

---
## 2018年におけるPHP

- モダンなPHPの主な仕事といえばAPIサーバー
 - ajaxで呼ばれてjsonを返す
- テンプレートエンジンでHTMLを返す
 - Twig, Jade

---

## 2018年におけるWeb

- とりあえずインタラクティブ
- とりあえずajax
- なんにせよ動く

---

<div class="attention font-big">
PHPは静的ページしか  
提供できない
</div>

---

<div class="attention font-big">
JSが必要
</div>

---

## やりいこと ＝ APIを作ること？

- フロントを作るのが好きな人もきっといるはず
 - とはいえjQueryはつらい
 - BootStrapでは物足りない
 

そんなあなたに是非今日のセッションを聞いてほしい

Note:
- APIがないとフロントエンドは成り立ちません  
いつも感謝しています
- フロントを作るのも楽しいぞっていう方に聞いてほしい
- フロント？jQueryだよね？っていう人にも

---

# なぜ「Vue.js」？

---

## 2018年における<br>Frontend Framework 3選

 Angular.png
 React.png
 Vue.png

激動の2015〜2017年を経て  
この3つで落ち着いてきた

Note:
- GoogleのトレンドグラフだとReactがダントツ
- 次はAngular、ちょっとあけてVue.jsがきてる
- backbone.js？あいつは４番目
- Github Star数は先日Vue.jsがReactを抜きました！

---

## どれがいい？

「Laravel with Vue」
```
While Laravel (中略) does provide a basic starting point using 
Bootstrap and *Vue* that will be helpful for many applications. 
```

あのLaravelがVueを公式にプロジェクトに含めている！

---

## Vueはいいぞ

Vue.png

---

<div class="attention font-big">
はい。
</div>

---

# Vueの始め方 Laravel編

---
## Laravelで始めるVueの環境構築
- ……は、Qiitaに書いたのでダイジェストで
- [LaravelからVue\.jsを使う最短レシピとTips \- Qiita](https://qiita.com/fruitriin/items/e0f2c9aa035c3ff2c874)
- 新規Laravel5.6プロジェクトから3ステップでOK

---
## 最短レシピダイジェスト
### Vueをインストール
- Projectのディレクトリへ移動してnpm install
```
npm install
```
- laravelの package.json に従ってインストール
 - composer.json みたいなやつ

---
## 最短レシピダイジェスト
### Bladeを修正
- jsとcss読み込み用のタグを追加
- CSRFトークンをVue.jsへコードを追加
 - コードは割愛！それぞれ一行追加でOK

---
## 最短レシピダイジェスト
### 開発環境を起動
- LaravelとVueの開発環境を起動
```
php artisan serve &
npm run dev
```
- いろいろいい感じにしてくれる

---

# Vue.js Live Coding 

Note:
ライブコーディングしていきましょう
---
## リアルタイム更新

HMR.gif

- テンプレート部分を編集して保存すると即反映
- ブラウザのリロードなしで確認
 
地味に便利！

- methodsの編集とかは読み込まれないことがある
---
## 変数展開と双方向バインド

variable-bind.gif

- `{{hoge}}` で変数展開
- `<input v-model="hoge">` で双方向バインド

めっちゃ便利！

---
## イベントとメソッド

event-and-methods.gif

- タグに `v-on:click="show()"` でクリック時にshow()
 - click, change, submit... DOMのイベントハンドラ

---
## 表示/非表示、配列とオブイェクトのループ

if-and-loops.gif

- タグに `v-if="isShow"` で表示非表示
- タグに `v-for="elem in elems"` でループ表示
 - 配列の要素、オブジェクトの要素どっちもOK！

---

<div class="attention font-big">
Vue.js はいいぞ！
</div>

Note:
めっちゃよくないですか？


---

# Vueを始める４つのヒント

Note:
- 小さく始めよう
- 大きくしよう
- これだけ覚えるべきES6
- jQueryと併用するべからず

---
## 小さく始めよう
- 最初はライブラリを極力入れないのがおすすめ
 - 「Vue + Vue-router + Vuexがデフォ？」  
「一度忘れていいよ」
- シングルコンポーネントで作る
 - コンポーネント分割は慣れてから

---
## 大きくしよう
- vue-cli でプロジェクトを作って構成を見比べる
 - vue-cli-ui がまじですごい

- 重厚なWAFっぽいのに乗っかりたかったらNuxt

---

## 大きくしよう
### Nuxt？
- Vue関係全部入りフレームワーク
- ゴリゴリフロントやるならNuxtで決まり
- 静的サイトジェネレータ機能
 - SSRに用事がなくてもNuxtはいいぞ
- 「PHPどこいった？」「APIです」「(´・ω・｀)」

---

## これだけは覚えるべきES6
- 変数宣言 let, const
- テンプレートリテラル
- アローファンクション
- Objectのメソッド

ES6(ES2015)チートシート - Qiita
https://qiita.com/morrr/items/883cb902ccda37e840bc

---
## jQueryと併用するべからず
- JSでDOMを直接書き換えると非常に危険

```
Virtual DOMの基本アプローチは仮想DOM -> 生のDOM変換であり、
この手続に依存する限り生DOMを触ることは推奨されません。
patchに巻き込まれると、知らないうちに
イベントハンドラごと吹き飛ぶ可能性があります。
しかも内部のアルゴリズムに依存するので非常にデバッグ困難です。
```
なぜ仮想DOMという概念が俺達の魂を震えさせるのか - Qiita (@mizchi)
https://qiita.com/mizchi/items/4d25bc26def1719d52e6

---
# My Fails of the Vue

- 単数形と複数形の間違い
- メソッドの階層間違い
- 「Main」コンポーネントは作れない
- なんでもアロー関数にしたらだめだった


---
# My Work

MasterViewer.vue.gif

---

<div class="attention font-big">
さあVue.jsを  
やってみよう！
</div>
<div class="date">
Thanks.
</div>