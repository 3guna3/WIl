## JSONとは
JavaScript Object Notationの略

JavaScriptを超えて、PHPやさまざまな言語で使うことができる

キーと値を設置して使う！

JSONはキーと値の順番が違ったり、データがないようなものでも動作する！

JSONのデータはfor構文などで配列として使うこともできる

例：JSONのデータ形式
```JavaScript
<script>
      const locations = [
                 {
                    "name": "国会議事堂",
                    "address": "東京都千代田区x-x-x"
                 },
                 {
                    "name": "札幌時計台",
                    "address": "札幌市中央区x-x-x"
                 },
                 {
                    "name": "首里城",
                    "address": "沖縄県那覇市x-x-x"
                 }
               ];
        for (let i=0; i<locations.length; i++) {
             document.write(locations[i].name + '/'
                            + locations[i].address + '<br>')
             }
</script>
```

## 同じようなデータの種類
### CSV(Comma Sepalated Values)
各データが何を表しているか分かりづらい、、、
順番が変わってしまったりするとデータが変わってしまう、、、
例：
```
<locations>
  <location>
    <name>国会議事堂</name>
    <address>東京都千代田区x-x-x-</address>
  </location>
  <location>
    <name>札幌時計台</name>
    <address>札幌市中央区x-x-x</address>
   </location>
</locations>
```

### XML(EXtensibe Markup Language)
データの本体以外のものが多くなってしまいデータが多くなってしまう、、、
