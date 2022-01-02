## XSS(クロスサイトスクリプティング)攻撃のセキュリティリスク

### XSSとは
- ユーザーの入力データを表示する箇所のHTML生成の実装に不備があると発生する脆弱性
- ユーザーが入力した内容を表示する箇所ではXSS対策は必須

### XSSへの対策

**特殊文字をエスケープする**
- HTMLの文法上特別な意味を持つ特殊記号を文字列参照に置き換える
- (例) < → `&lt;` > → `&gt;`

## PHPでXSS対策するには
**htmlspecialchars() を使ってHTML特殊記号をエスケープする**

- HTML特殊記号を文字参照に置き換える
  - $string :　変換する文字列
  - $flags : 処理の仕方を指定するフラグ
  - $encoding : 文字列を変換するときに使用するエンコーディング
```php
htmlspecialchars($string, $flags, $encoding)
```

- ユーザーが入力してDBに保存された「<script>・・・</script>」の値をエスケープするなら
```php
htmlspecialchars('<script>・・・</script>', ENT_QUOTES, 'UTF-8')

# 実行結果
&lt;script&gt,・・・&lt;/script&gt;
```
