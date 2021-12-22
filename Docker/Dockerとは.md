## Dockerとは

- 仮想環境を作成するためのプラットフォーム

### 仮想環境がないと

- Aさんの環境では動いたのに、Bさんの環境では動かない
- 開発環境では動いたのに本番環境では動かない
- 開発環境のセットアップに時間がかかる

### Dockerを使うと

- 他の人の環境でも動作する
- 開発環境と本番環境を合わせやすい
- 開発環境のセットアップが簡単

## Dockerの基本的な仕組み

## Dockerイメージ
- コンテナの元になるテンプレート
- OSや実行するアプリケーションや設定をまとめたもの

**操作手順**
- DockerイメージからDL or ベースをDockerレジストリからDLして自分が導入したいライブラリなどを組み込んでビルドして自分でDockerfileを作る

## Dockerコンテナ
- Dockerイメージをもとに作成される
- OSとアプリケーションが動く実行環境

**操作手順**
- コンテナを生成し起動する

## Docker操作コマンド

- 取得　 `$ docker image pull`
- ビルド `$ docker image build`
- 生成  `$ docker container create`
- 起動　 　`$ docker container start`
- 停止  `$ docker container stop`
- 削除  `$ docker container rm`

## 複数のコンテナを動かしたいときは？

### Docker Compose
- Dockerでは1つのコンテナには1つの役割という決まりがある
- Docer Composeは複数のコンテナを定義し、実行するツール

**操作コマンド**
- ビルド　`$ docker-compose build`
- 生成・起動　`$ docker-compose up`
- 停止 `$ docker-compose stop`
- 削除 `$ docker-compose rm`

### よく使うコマンド

- 起動中のコンテナでコマンドを実行 `$ docker-compose exec`
- コンテナの一覧を表示 `$ docker-compose ps`
- ログを表示 `$ docker-compose logs`
- 使用していないコンテナ、イメージを削除 `$ docker system prune`
