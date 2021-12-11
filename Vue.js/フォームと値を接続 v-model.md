## フォームと値を接続する v-model

Vue.jsを使用することでフォームとの連動が非常に簡単にできる

<例>
```html
<div class="frame_inner">
  <div id="app">
    <!--v-model="number"とすることでdataで定義したnumberとテキストフィールドの内容が連動するようになる-->
    <input type="number" v-model="number"> = {{ number }}
  </div>
  <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  <script>
    var app = new Vue ({
        el: "#app",
        data: {
            number: 999,
         },
     });
  </script>
</div>
```

### v-modelについて
`v-model`は`:value`と`@input`の指定を省略した書き方　　

[公式ガイド](https://jp.vuejs.org/v2/guide/components.html#%E3%82%B3%E3%83%B3%E3%83%9D%E3%83%BC%E3%83%8D%E3%83%B3%E3%83%88%E3%81%A7-v-model-%E3%82%92%E4%BD%BF%E3%81%86)

例えば

```vue
<input v-mpodel="searchText">
```
これは以下と同じ意味となる
```vue
<input
  :value="searchText"
  @input="searchText = $event.target.value"
>
```
`:value`はsearchText変数の値を読み込んでフォームに表示するためのプロパティ  
`@input`はフォームの値が変更された時に実行する処理を指定するプロパティ  
`$event.target.value`にはそのフォームに入力された値が入り、その値をsearchTextに代入している  
このように、読み込みと書き込みの処理を分けて書くことができる！  
  
ただし、カスタムコンポーネントで使用する場合は`$event.target.value`でなく`$event`を使用する
