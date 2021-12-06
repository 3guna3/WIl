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
