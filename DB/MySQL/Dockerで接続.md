## DockerでMySQLに接続するには

**DockerではappコンテナとDBコンテナが定義されていて、appコンテナからDBコンテナに接続する**

**MySQLと接続するにはmysqlコマンドを使用する**

- クライアントからmysqlサーバーに接続する
  - -h :host ホスト名
  - -u :user ユーザー名
  - -D :database データベース名
  - -p :password  
`mysql -h ホスト名 -u ユーザー名 -D データベース名 -p`

- appコンテナからdbコンテナのmysqlに接続する  
`docker-compose exec app mysql -h db -u book_log -D book_log -p`
