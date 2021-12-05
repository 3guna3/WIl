## cookie処理

### cookieの基本

クッキーとはString型の文字列
HTMLDocumentのプロパティとして実装されているので、`document.cookie`でアクセスできる。

### 書式

クッキーは`名前=値`の形で書く  
<例>
```js
// data1という名前のcookieに123という値をセット
document.cookie = 'date1=123'
```

### エンコード
クッキーの名前や値にはセミコロン(;)やカンマ(,)空白は含めてはならない。  
**encodeURIComponent()** を使用すること

### パラメータ
いくつかの属性を設定することができる

**path**  
クッキーが有効なパス

**domain**  
クッキーが有効なドメイン

**max-age**  
クッキーの有効期限(秒数で指定,設定しないとブラウザ終了時に削除)

**expires**  
クッキーの有効期限(日付で指定,設定しないとブラウザ終了時に削除)

**secure**  
セキュリティの設定

## <例>Cookieにメールアドレスを保存して、次回自動入力する

```html
<div>
  <input type="text" id="email" name="email">
<div>
<button id="save">メールアドレスを保存する</button>
  
<script>
  // cookieを加工する処理
  const getCookie = (key) => {　
  
      // cookieに保存する内容が複数ある場合
      let cookies = document.cookie.split(';');
  
      for (let i = 0; i < cookies.length; i++) {
          let k = cokkies[i].split('=');
          if (k[0] === key) {
                                         
              // コードを元に戻すため、decodeURIComponent関数を使う
              return decodeURIComponent(k[1]);
          };
      };
      // 下記のようにすることで、cookiesに何も入っていなかった場合や、指定されたkeyが見つからなかった場合にから文字を返す
      return '';
   };
   document.getElementById('save').addEventListener('click', function() {
             
            // encodeをかけて@や;を保存できるようにする
            let email = encodeURIComponent(document.getElementById('email').value);
                   
             document.cookie = 'email=' + email + '; maex-age=3600';
             document.cookie = 'mynum=123; max-age=3600;'
         });
                          
   // ユーザーがcookieの値を使えるようにする
   document.getElementById('email').value = getCookie('email');
</script> 
```
