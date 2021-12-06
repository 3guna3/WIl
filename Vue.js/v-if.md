## 条件によって、表示・非表示を切り替える v-if

`v-if`を使うことで要素の表示・非表示を簡単に切り替えることができる

<例>
```html
<div class="frame_inner">
  <div id="app">
    <!--v-ifでout_serviceがtrueであればpタグの要素を表示し、falseであれば表示しないとする-->
    <p class="alert" v-if="out_service">現在は営業時間外です</p>
  </div>
  <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  <script>
    // 時間で表示・非表示を切り替えるための処理
    const today = new Date();
    let hour = today.getHours();
    
    var app = new Vue ({
        el: "#app",
        data: {
            out_service: hour > 20,
        }
    });
  </script>
</div>
```
 
