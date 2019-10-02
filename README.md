# docker compose を使用した Rails6 Template

### According to docker docs(Rails QuickStart)

> [docker docs (Rails Quickstart)](https://docs.docker.com/compose/rails/)

## 1.プロジェクトの構築

`docker-compose run web rails new . --force --no-deps --database=postgresql`

## 2.新しい Gemfile の為の再ビルド

`docker-compose build`

## 3.データベースの設定

> Replace the contents of `config/database.yml` with the following:

```
default: &default
  adapter: postgresql
  encoding: unicode
  host: db
  username: postgres
  password:
  pool: 5


development:
  <<: *default
  database: myapp_development


test:
  <<: *default
  database: myapp_test
```

## 4.データベースの作成

`docker-compose run web rake db:create`

## 5.アプリの起動

`docker-compose up`

## 6.アプリの停止

`docker-compose down`

## 7.アプリの起動

`docker-compose up`
