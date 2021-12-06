## v-onディレクトリでイベントを作る

### <例>１度クリックされると押せなくなるボタン
```html
<div id="app">
  <!--disbandでscriptタグ内のclickedを指定、clickedがtrueであればボタンが押せなくなり、falseだとボタンが押せる-->
  <!--v-onはイベントを定義するもの、@で省略して定義できる-->
  <button @click="checkClick" :disabled="clicked">決済する<button>
</div>
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
  var app = new Vue ({
      el: "#app",
      data: {
          clicked: false,
      },
      // 処理をメソッドとして定義
      method: {
          checkClick: function() {
              // ここのclickedはscliptタグ内で定義したclickedなのでthisとする
              this.clicked = true
          },
      },
  });
</script>
```
