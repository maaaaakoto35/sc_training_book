# Level1 Web

これはスマートキャンプで主に使っているフレームワークやライブラリでのWebアプリケーション開発について学んでいきます。

この課題では以下の習得を想定しています。

- Ruby on Rails
  - 初期構築方法
  - MVCの設計
  - Migration使い方
  - ActiveRecord使い方
  - Slim使い方
  - N+1の解消
- Vue.js
  - SPA構成
  - Webpack使い方
  - コンポーネントの作り方
  - axiosの使い方
- Docker
  - docker-composeの使い方


## 事前準備

- Ruby: 2.7.1
- Node: 14.17.3
- MySQL
- Docker

## やり方

**必ず課題毎にPRを作成し、誰かからレビューを受けてください。**
疑問点などもPRに記載し答えてもらいましょう。

課題と課題はともに依存しているので、同じブランチから派生するようにしましょう。

例) master -> step1 -> step2 -> step3

## 課題

### 1. Railsを立ち上げてみよう！

- Rails６
- MySQL

#### チェック項目

- [ ] http://localhost:3000/ でアクセスしてWelcomeページが表示されるか

### 2. 1ページ追加してみよう！

- Slim(TemplateEngine)のインストール
- route.rbに追加
- controllerにactionを記述
- viewにファイルを追加

#### チェック項目

- [ ] http://localhost:3000/hello_world でアクセスして適当なページが表示されること

### 3. データベースにテーブルを2つ追加してみよう！

- dbへのアクセス設定
- database作成
- migrationファイルを作成
- migrationファイルにtable作成コード記述
- migrate実行

*テーブル*
```
Users
+id bigint
+corporation_id bigint
+email varchar(255)
+admin tinyint(1)
+updated_at timestamp
+created_at timestamp
```

```
Corporations
+id bigint
+name varchar(255)
+updated_at timestamp
+created_at timestamp
```

#### チェック項目

- [ ] Migrationがエラーなく通ること
- [ ] MySQLにアクセスし、DatabaseとTableが生成されていること

### 4. Modelを作成し、Seedでデータを入れてみよう！

- table分だけmodelファイル作成
- modelに関連を記述
- seedsファイルを作成
- seeds実行(※ Corporation:2, User:4くらいは作る)

#### チェック項目

- [ ] `rails c` のコンソールで `Corporation.count` がSeed作成したレコードと一致しているか
- [ ] `rails c` のコンソールで `Corporation.first.users` で取得できるか
- [ ] `rails c` のコンソールで `User.first.corporation` で取得できるか

### 5. Corporation一覧を表示するページを作成してみよう！

- route.rbに追加
- corporation用のcontrollerを別に作成
- viewファイルを作成
- controllerでcorporationsを取得
- viewでcorporationsを一覧表示

#### チェック項目

- [ ] http://localhost:3000/corporations にアクセスし、会社一覧が表示されること

### 6. Corporationを作成するページを作成してみよう！

- route.rbに追加(作成ページ取得:GET, 作成:POST)
- controllerにactionを追加
- viewファイルを作成
- viewにフォーム追加
- controllerに作成処理実装

#### チェック項目

- [ ] http://localhost:3000/corporations/create にアクセスし、作成画面が表示されること
- [ ] http://localhost:3000/corporations/create で会社名を入力し、送信するとCorporationが追加されること


