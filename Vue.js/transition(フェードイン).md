## フェードインで表示する transition

<例> フェードインで要素を表示させる

```html
<style>
  /* v-enter-activeというクラス名はVue.jsによって勝手に付加されるもの */
  .v-enter-active {
      transition: opacity 1s;
  }
  .v-enter {
      opacity: 0;
  }
  .v-enter-to {
      opacity: 1;
  }
  /* このほかにも
  .v-leave, .v-leave-active, .v-leave-toといった
  要素を非表示にするものもある */
  
</style>

<div class="frame_inner">
  <div id="app">
    <!--フェードインするアニメーションを作成-->
    <transition appear>
      <div v-html="message"></div>
    </transition>
  </div>
  
  <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  <script>
    // Vue.jsではvarを使うのが一般的
    var app = new Vue ({
        el: "#app",
        data: {
              message: "Vue.jsを勉強しています",
        }
    })
  </script>
</div>
```
