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

### クリックイベントとイベント修飾子

HTML要素がクリックされたときに、重ね合わさった要素の子から親へとクリックイベントが伝わっていくという仕組みが元々備わってる例えばノートの編集ボタンをクリックすると、裏側にある左ビューもクリックされた扱いとなる、といった形  

今回は左ビューがクリックされたときに編集終了としたいのですが、単純に`@click="onEditNoteEnd()"`とすると、編集ボタンをクリックしたイベントが親である左ビューまで伝わることで`onEditNoteEnd`が即座に呼ばれてしまい、編集状態がすぐに終了してしまうというバグが発生してしまいます。

そこで、`@click.self`のようにクリックイベントの後半部分に`.self`という箇所を追加することで、「子から伝わったイベントではなく、左ビュー自体がクリックされた場合のみ動作する」という仕組みが実現可能となります。

このようにイベントディレクトティブの後半に付与することで、挙動を制限するものを「イベント修飾子」と呼びます。

参考：[Vue.js公式 : v-on](https://jp.vuejs.org/v2/api/index.html#v-on)
