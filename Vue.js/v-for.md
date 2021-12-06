## v-forディレクティブで繰り返し構文を作る

非常に簡単なプログラムの場合、Vue.jsのプログラミング部分にはほとんど何も書かず、ディレクティブだけでいろいろなプログラムを組むことができる。

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
