## HTML属性にVue.jsで値を挿入する -v-bind

<例>

```htnl
<style>
        .error {
            color: red;
        }
        
        .success {
            color: green;
        }
</style>

<div class="frame_inner">
  <div id="app">
    <!-- classの前に:をつけるとVue.jsで書き換えたいということになる-->
    <!-- :でclassを書くのをディレクティブという-->
    <!-- Vue.jsではこのディレクティブを多用して書いていく-->
    <p :class="error_class">赤文字で警告</p>
  </div>
</div>

<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script>
        let app = new Vue({
            el: '#app',
            data: {
                error_class: 'success',
            },
        })
     </script>
```
属性にVue
