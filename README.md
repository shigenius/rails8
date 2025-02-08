# Description
Example of rails on docker-compose.

# Prepare
* docker-composeコマンドが使えること

# Usage
## とりあえずサーバー起動までの手順
```sh
$ git close git@github.com:shigenius/rails8.git
$ cd rails8
```
### DB初期化

```sh
$ docker-compose run --rm web bundle exec rails db:create
```

### railsサーバー立ち上げ

```sh
$ docker-compose up
```

* http://localhost:3000/ にアクセスできたらok
* サーバーを実行しているコンソール上で、ctrl+cでサーバーをストップ

## その他コマンド
### （すでに作成されている）webコンテナに入る

```sh
$ docker compose exec web bash
```

## 一時的なwebコンテナを作成してbashを実行

```sh
$ docker-compose run --rm web bash
```

* tips: `--rm`オプションが付いているので、セッションを終了したときにコンテナも終了する

## バックグラウンドでサーバーを立ち上げる場合

```sh
$ docker-compose up -d
```

## サービス停止

```sh
$ docker-compose down
```