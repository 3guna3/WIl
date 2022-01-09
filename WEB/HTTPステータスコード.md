### 2xx系
**リクエストが成功したことを表す**

- 200
  - [意味] ok

- 201
  - [意味] Created

- 204
  - [意味] No Content

### 3xx系
**リダイレクトを表す**

- 301
  - [意味]Moved Permanently 「URLが変わったよ」

### 4xx系
**クライアントエラーを表す**

- 400
  - Bad Request 「You, リクエスト間違ってるよ？」

- 401
  - Unauthorized 「You, 誰？」
  - ログインが必要なページにログインせずにアクセスしようとするなど

- 403
  - Forbidden 「You, 君はダメだよ？」
  - 管理者のみのコンテンツに一般ユーザーがアクセス

- 404
  - Not Found 「You, それはないよ？」
  - 存在しないページ

### 5xx系
**サーバーエラーを返す**

- 500
  - Internal Server Error　「Me, 具合が悪い」

- 503
  - Service Unavaliable 「Me, 忙しすぎて目が回った」










