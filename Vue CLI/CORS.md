## CORSとは

- Cross-Origin Resource Sharingの略
- 異なるオリジン感でリソース(データ)を共有したいときに、自身とは異なるオリジンにリソースのアクセスを許可する仕組み
- CORSの設定を行わないと、Railsなどは他のオリジンからのアクセスを拒否するため、API通信ができない
- なのでRail側で`http://localhost:8080`からのリクエストを許可する必要がある


### CORSの設定

- Gemfileに`# gem 'rack-cors'`と書かれているものがあるので、その行のコメントを外す
- bundle installを実行
- `/config/initializers/cors.rb`を書き換える

```rb
Rails.application.config.middleware.insert_before 0, Rack::Cors do
    allow do
      #ここを変更　origins 'example.com'
      origins 'http://localhost:8080'

      resource '*',
        headers: :any,
        methods: [:get, :post, :put, :patch, :delete, :options, :head]
    end
  end
```
