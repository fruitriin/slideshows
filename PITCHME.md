## 私がハマった<br>Vue.jsのショボいミス
<center>果物リン@fruitriin</center>
<div class="footer">2018/06/某日</div>

---

### 自己紹介 果物リン@fruitriin

- 株式会社ORATTA所属  
ソーシャルゲーム開発・運営
- サーバーサイドエンジニア  
ぺちぺちしている
- JSが好き  
Vue.jsはいいぞ！

---

## 流石にしょぼすぎて<br>誰もかかないことを<br>あえて書く！

---
## Case1. ESLintうざい
- vue-cliが入れる？って聞かれたから入れてみた
- とにかく全部指摘されてうざい
- こういうもんなの？

**eslint --fixで自動整形とかできます**  
**詳しくはWebで！**  
<div class="footer">*それはそれでやっぱりちょっとうざい*</div>

---

## Case2. アロー関数とスコープ

- ES6だし関数全部アロー関数で書いてみようぜ！
- methods直下etcで アロー関数使ってみた
- dataにthis.hogeで値を取ろうとして undefiend

---?image=bg/navy.png
### サンプルコード
```
var app = new Vue({
  data: () => { 
    return { msg : "Hello Vue"}
  },
  methods:{
    myFunc: ()=>{
      console.log(this.msg)
    },
  })
})
```
@[2-4](これはセーフっぽい？)
@[6-8](この書き方に注目！)

---?image=bg/navy.png
### call myFunc
```
<button v-on:click="myFunc">{{msg}}</div>
```

→ undefiend

---?image=bg/navy.png
### メソッドが this. でアクセスできない
<center>
![](assets/598x375xe4022b20b838933f265c1591.jpg)

</center>

---

### どういうこと？
- アロー関数は this を束縛しない
- 本来はthisをこのコンポーネントで束縛したい

→ this が親スコープを指す

---

### data, methodsの正しい使い方
```
var app = new Vue({
  data: function() { 
    return { msg: "Hello Vue"}
  },
  methods:{
    myFunc(){
      console.log(this) 
    },
  })
})
```
@[2-5](プロパティ = 関数として定義する記法)
@[7-0](クラスのメソッド風として定義する記法)

アロー関数を使わない方法二通り

---

### アロー関数の使い所

```
data() {
  return { hoge: "fuga"}
}
methods: {
  myFunc(data){
    axios.post("http://example.com/sampleApi",(res)=>{
      console.log(res)
      console.log(this.hoge);
    })
  }
}
```
コールバックとかに使うといいぞ！
@[6-9](コールバックにアロー関数)
@[2,8](thisでhogeにアクセスできる)

---
### Case3.単数形と複数形の間違い
- propで呼び出し元から値を受け取ろう
- あれ？絶対あるはずのものがない
- あれ？あれ？あれれれ？

**正しいエントリポイントは  
props, components, methods等です**  
*間違えてもなんの警告もでない*

---

### Case4. メソッドの階層間違い
- 新しいメソッドを生やそう
- あれ？絶対あるはずのものがない
- あれ？あれ？あれれれ？

**methodsの直下が各メソッドの正しいエントリポイントです**  
*うっかりメソッドを生やす階層を間違えた*

---

### Case5. 「Main」コンポーネント
- なんかVue.js側が使ってるらしくてうまくいかない？
- 特にエラーも出ずにただ使えなかった気がする
- 前述の"Component"って書いてたせいのような気もしてきた。あとで試す

---

### Case6. or more...
- 何かあるたびに追加していきます

---

## それでも<br>Vue.jsはいいぞ

---

## Thanks.

<style>
.footer{
    display:block;
    position:relative;
    bottom:0em;
    right:1em;
    float:right;
}
.slides section{
    text-align:left;
}
.slides section h1, .slides section h2, 
.slides section h3, .slides section h4,
 .slides section h5, .slides section h6
{
    text-align:center;
}
.right{
    text-align:right;
}
.layout-right{
    float:right;
}
.layout-left{
    float:left;
}
</style>
