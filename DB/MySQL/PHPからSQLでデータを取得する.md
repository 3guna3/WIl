## PHPからSQLでデータを取得する

**QL文を実行した結果のデータを取得するにはmysqli_fetch_assocを使う**
```php
$link = mysqli_connect('my_db', 'my_user', 'my_password', 'my_Db'); //　DBに接続
$sql = 'SELECT name, founder FROM companies';
$results = mysqli_query($link, $sql); // SQL文を実行

while ($company = mysqli_fetch_assoc($results)) { // 連想配列で結果を取得
  echo '会社名 : ' .$company['name'] . PHP_EOL;
  echo '代表者 : ' .$company['founder'] . PHP_EOL;
}

mysqli_free_result($results);  // メモリを解放する
```
