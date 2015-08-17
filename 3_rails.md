# 3. Ruby on Railsの基礎

Ruby on Rails(以下Rails)は、プログラミング言語Rubyで書かれたWebアプリケーション
フレームワークです。

Railsで *Blog* という名前のWebアプリケーションをつくりながら、Railsを学習していきましょう。

## (1) アプリケーションの作成

### アプリケーションを作成する
```
$ cd /var/share
$ mkdir Blog
$ cd Blog
$ bundle init
```
.bundleというディレクトリと、Gemfileが作成されます。

```ruby
gem 'rails'
```

```
$ bundle install --path vendor/bundle
$ bundle exec rails new .
$ bundle
```

### ブラウザから確認する
Webサーバー(WEBlick)を起動します。
```
$ bundle exec rails s -b 0.0.0.0
```
http://192.168.56.101:3000 にアクセスして、*Welcome aboard*ページが表示されたらOKです。

Webサーバーの停止は、<code>Ctrl+C</code>で行います。

## (2) "Hello World"を表示する

Railsで"Hello World"と表示するためには、少なくともControllerとViewが必要です。

## (3) 記事管理ページを作成する

## (4) 画面をデザインする

いまのままの画面はイケてないので、Bootstrapを利用して、画面をデザインしてみましょう。

## (5) 自分のブログサイトをつくる


## 参考

- RailsアプリのデータベースにMySQLを利用する
  ```
  $ bundle exec rails new . -d mysql
  ```
  ```
  Gemfile
  gem 'mysql2'
  ```

- Railsアプリをapache2と連携させる
  ```
  $ passenger-install-apache2-module --snippet
  ```
