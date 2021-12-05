## TypeScriptでトランスコンパイル

### 方法

まず処理を`.ts`の拡張子がついたファイルに書き込む

ex. sampele01.ts
```ts
let message = 'TypeScriptを勉強中です'

console.log(message)
```

その後ターミナルから
```
tsc sample01.ts
```
と入力


そうすると自動でsample01.jsというファイルが作成される

ファイルの中身はトランスコンパイルされた形式となっている
```js
var message = 'TypeScriptを勉強中です'
console.log(message
```

このように簡単にトランスコンパイルできる！
