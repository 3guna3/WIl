## PHPからMySQLに接続する

**PHPからMySQLを利用するときはMySQLiを使う(※オブジェクト指向学習前)**
- MySQLに接続するにはmysqli_connect関数を使う  
`mysqli_connect('my_host', 'my_user', 'my_password', 'my_db')`

### MySQLに接続できない場合
**MySQLに接続できない場合が想定されるので、対策しておく**

- mysqli_connect()は接続に失敗した場合にFALSEを返すので、これを利用してアプリケーションを終了させる  
```
$link = mysqli_connect('my_host', 'my_user', 'my_password', 'my_db');
if (!$link) {
  echo 'データベースに接続できません'. PHP_EOL;
  echo 'Debugging error:'. mysqli_connect_error() . PHP_EOL;
  exit;
}
```

## PHPからMySQLにデータを追加する

**SQLのINSERT文でテーブルにデータを追加する**

- INSERT文を使うと、テーブルに１行のデータを挿入する
  - $link : mysqli_connect()が返すリンクID
  - $query : SQL分の文字列  
`mysqli_query($link, $query)`

- companiesテーブルにデータを登録するなら
```
$link = mysqli_connect('my-host', 'my-user', 'my-password', 'my-db' );
$sql = "INSERT INTO companies(name) VALUES ('SmartHR inc')";
mysqli_query($link, $sql);
```

### SQL文実行時にエラーがあった場合、エラ〜メッセージを表示する
- mysql_query()は実行に失敗した場合、FALSEを返すことを利用してエラーメッセージを表示させる
```php
$link = mysqli_connect('my-host', 'my-user', 'my-password', 'my-db' );
$sql = "INSERT INTO companies(name) VALUES ('SmartHR inc')";
$result = mysql_query($link, $sql);

if (result) {
  echo 'データを追加しました'. PHP_EOL;
} else {
    echo 'Error: データの追加に失敗しました'. PHP_EOL;
    echo 'Debugging error:'. mysqli_error($link). PHP_EOL;
}
```

### ヒアドキュメントを使うことで複数行にまたがる文字列を表記できる
- ヒアドキュメントを使うと、複数行の文字列をそのままコード内に記載できるので、SQLを書くときに見やすくなり便利
```sql
$sql = <<<EOT
INSERT INTO companies (
  name
) VALUES (
  'SmartHR inc'
)
EOT;
```

