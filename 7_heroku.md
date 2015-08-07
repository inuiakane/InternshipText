# アプリをインターネットに公開する

作ったRailsアプリをHerokuにアップして、インターネット上に公開してみましょう。

HerokuはPaas(ソフトウェアを構築および稼働させるための土台となるプラットフォームを提供するインターネットサービス)で、無料で利用できるプランがあります。

## Herokuアカウントを取得する



## アプリケーションの準備

#### バージョン管理

git commit しておきましょう。

#### データベース

Herokuの標準データベースはPostgreSQLです。  
開発はMySQLを利用していましたが、HerokuではPostgresSQLを利用するようにします。<br>

また、HerokuでRails4を動かすために**rails_12factor**というgemが必要になります。

Gemfileを以下のように編集して、<code>bundle install</code>を実行してください。
```
group :development do
  gem 'mysql2'
end
group :production do
  gem 'pg'
  gem 'rails_12factor'
end
```
git commitも忘れずに実行します。

## Herokuへのデプロイ

#### Herokuにログインする
```
$ heroku login
Enter your Heroku credentials.
Email: アカウント作成時に登録したEメールアドレス
Password (typing will be hidden): パスワード
```

#### アプリケーションの作成

```
$ heroku create
Creating boiling-wildwood-7339... done, stack is cedar-14
https://boiling-wildwood-7339.herokuapp.com/ | https://git.heroku.com/boiling-wildwood-7339.git
Git remote heroku added
```
この場合は*boiling-wildwood-7339*というアプリ名が自動的につけられました。

#### プログラムをHerokuにpush

```
$ git push heroku master
Counting objects: 4736, done.
Compressing objects: 100% (3637/3637), done.
Writing objects: 100% (4736/4736), 10.43 MiB | 77.00 KiB/s, done.
Total 4736 (delta 705), reused 4736 (delta 705)
remote: Compressing source files... done.
remote: Building source:
remote:
remote: -----> Ruby app detected
remote: -----> Compiling Ruby/Rails
remote: -----> Using Ruby version: ruby-2.0.0
remote: -----> Installing dependencies using 1.9.7
remote:        Running: bundle install --without development:test --path vendor/bundle --binstubs vendor/bundle/bin -j4 --deployment

...

Verifying deploy... done.
To https://git.heroku.com/boiling-wildwood-7339.git
 * [new branch]      master -> master
```

#### データベースのmigrate

```
$ heroku run rake db:migrate
または
$ heroku run:detached rake db:migrate
```

### おまけ

herokuコマンドには以下のようなものがあります。

#### 再起動する
```
$ heroku restart
```

#### ログをみる
```
$ heroku logs --tail
```
