# 3. Ruby on Railsの基礎

Ruby on Rails(以下Rails)は、プログラミング言語Rubyで書かれたWebアプリケーション
フレームワークです。

Railsで *Blog* という名前のWebアプリケーションをつくりながら、Railsを学習していきましょう。

### アプリケーションの作成

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
```

```
$ bundle exec rails new . -d mysql
```
