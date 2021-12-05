## Vue.jsでプログラムを作成

<例>

```html
<div class="flame">
  <div class="flame_inner">
    <!-- Vue.jsは{{}}で囲む、これをマスタッシュ構文という -->
    <div id="app">{{ message }}</div>
  </div>
</div>

<!-- これでVue.jsを書くことができる -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

<script>
  let app = new Vue ({
      // elはエレメントなので、ここでは上のdiv id="app"の要素を取得
      el: "#app",
      data: {
           message: "Vue.jsを勉強しています",
      },
  })
</script>
```
