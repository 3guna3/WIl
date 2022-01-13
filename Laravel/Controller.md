## コントローラの定義

```php
<?php

namespace App\Http\Controllers;

use App\Http\Controllers\Controller;
use App\User;

class UserController extends Controller
{
  // 指定のユーザーのプロフィール表示
  
  public function show($id)
  {
    return view('user/profile', ['user' => User::findOrFail($id));
  }
}
```

コントローラアクションへルートをつけるには、次のようにする
```php
Route::get('user/{id}', UserController@show');
```

これで指定したルートのURIにリクエストが一致すれば、`UserController`の`show`メソッドが実行される。
ルートパラメータはメソッドに渡される。
