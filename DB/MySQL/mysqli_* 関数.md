### mysqli_query
- データベース上でクエリを実行する
- 成功したらmysqli_resultオブジェクトを返す  
`mysqli_query($link, $query)`

### mysqli_fetch_assoc
- 結果の行を連想配列で取得する
- $result : mysqli_resultオブジェクト  
`mysqli_fetch_assoc($result)`

### mysqli_free_result
- 結果に関連づけられたメモリを解放する
- $result : mysqli_resultオブジェクト  
`mysqli_free_result($result)`
