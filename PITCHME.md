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
---?image=assets/selfy.jpeg

## 自己紹介
![](assets/selfy.jpg)


- 株式会社ORATTA 
 - ソシャゲの開発運営
 - サーバーアプリケーションエンジニア
- 趣味JSer
 - Vue.jsはいいぞ！


---

## 株式会社ORATTA

<center>
![](assets/oratta.jpg)
</center>

戦国アスカZEROとか作ってます。  
PWA版『クイック』をリリースしました！(2018.6)

Note:
お勤めなのでちょっと自社の紹介させてください。
---

## 戦国アスカZERO

<center>
![](assets/asukazero.png)
</center>

なでなでするほど強くなるRPG  
App Store, Google Play, Chrome, Yahoo! Mobagee


---
## 全国CM打ちました(2017.9)
<center>
![](assets/asuka_cm.png)
</center>
この顔にピンときたらORATTAです。

---
## Next Project is Laravel
<center>
![](assets/laravel.png)
with Game
</center>

このロゴにピンときたらORATTAです？

Note:
このロゴとゲーム作りのキーワードにピンときたらORATTAです！

---
## We are Hireling

<center>
![](assets/oratta_logo.png)
</center>
このロゴにピンときたらORATTAです。
Note:
東京の会社ですが、ゲームづくりに興味がある人は会社のホームページも見てみてください。

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
- 付録

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
# 諸々組み合わせて

MasterViewer.vue.gif

---

<div class="attention font-big">
Vue.js はいいぞ！
</div>

---

# 付録

こんな記事を書いてます

- Vue.jsを始める4つのヒント - Qiita
- My Fails of the Vue - Qiita



---
<div class="attention font-big">
さあVue.jsを  
やってみよう！
</div>
<div class="date">
Thanks.
</div>


