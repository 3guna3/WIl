## v-forディレクティブで繰り返し構文を作る

非常に簡単なプログラムの場合、Vue.jsのプログラミング部分にはほとんど何も書かず、ディレクティブだけでいろいろなプログラムを組むことができる。  
`v-for`は変数や関数の返り値に格納された配列の各要素を1つずつHTML側に展開してくれるディレクティブ

`v-for`を使用する際は同時に`:key="キー"`といった形で、キー部分に一意なIDを渡す必要がある！

### 使い方
```js
v-for='変数名 in 配列'
```

### <例>1から365までの数字を表示する
```html
<div id="app">
  <ul v-for="i of 365" :key="i">
    <li>{{ i }}</li>
  </ul>
</div>

<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
  var app = new Vue ({
      el: "#app",
  });
</script>
```

`v-for`と使うときは`:key`もセットで使うこと！


## v-forディレクティブで配列を制御

### <例>曜日を出力する
```html
<div id="app">
  <!--weeksというscriptタグ内で定義した配列の中身をweekに1つ１つ入れていく-->
  <ul v-for="week of weeks" :key "week">
    <li>{{ week }}</li>
  </ul>
</div>
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
  var app = new Vue ({
      el: "#app",
      data: {
        weeks: ['日', '月', '火', '水', '木', '金', '土'],
      }
  })
</script>

```
