## PHPとHTMLファイルを分割

**include**
- 指定したファイルを読み込む
  - 読み込みが失敗しても処理が中断されない
  - HTMLやテキストなどを読み込む際に使用
```php
include 'somefile.php';
```

[参考]
**require_once** 
- 指定したファイルを読み込む
  - 読み込みが失敗したら処理が中断され、一度しかファイルを読み込まない
  - 関数などの重要な処理を読み込む際に使う
```php
require_once 'sample.php';
```
