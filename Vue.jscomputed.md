## computedとは

- dataと同じように宣言できるが、その内容をプログラムとして書くことができるという違いがある

### <例>計算機プログラムを作る(イベントを使った書き方)

```html
<div id="app">
  <!--v-modelの後に.numberとすることで数字と認識される-->
  <input type="number" name="num1" v-model.number="num1" @change="calc" /> +
  <input type="number" name="num2" v-model.number="num2" @change="calc" /> =
  <!--マスタッシュ構文でanswerを呼び出す-->
  <span>{{ answer }}</span>
</div>

<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
  var app = new Vue ({
      el: "#app",
      data: {
          num1: 0,
          num2: 0,
          answer: 0,
      },
      // calcという計算をするメソッドを定義
      method: {
          calc: function() {
              this.answer = this.num1 + this.num2
          },
      },
  }),
</script>
```

### 上記をcomputedを使って書き換え

```html
<div id="app">
  <input type="number" name="num1" v-model.number="num1" /> +
  <input type="number" name="num2" v-model.number="num2" /> =
  <span>{{ answer }}</span>
</div>
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
  var app = new Vue ({
      el: "#app",
      data: {
        num1: 0,
        num2: 0,
      },
      // computedはdataと同じように宣言して、その内容をプログラムとして書くことができるという違いがある
      computed: {
          // answerを呼び出すだけでthis.num1 + this.num2の結果を返すことができる
          answer: function() {
               return this.num1 + this.num2
          },
      },
  })
</script>
```
