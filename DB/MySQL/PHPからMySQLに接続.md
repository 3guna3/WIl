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
