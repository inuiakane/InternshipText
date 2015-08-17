# 1. インストール

Ruby on RailsでWebアプリケーションをつくるための開発環境を構築しましょう。<br>
このテキストでは、仮想マシン(VM: Virtual Machine)に開発環境を構築する方法を説明しています。

## 環境

* Host: Windows
* Guest: Ubuntu 14.04 LTS

## 開発するためのツールをインストールする

Railsで開発するときには、以下のソフトウェアを使います。  
最初にホストマシンにインストールしておきましょう。

- テキストエディタ: [Atom](https://atom.io/)

- SSHクライアント: [Teraterm](http://osdn.jp/projects/ttssh2/releases/)

- Webブラウザ: [Chrome](https://www.google.co.jp/chrome/browser/desktop/)

## ゲストOSの構築

1. VirtualBoxのインストール

  仮想マシンを利用するために、仮想環境を構築するためのソフトウェア[VirtualBox]( https://www.virtualbox.org/wiki/Downloads)をホストマシンにインストールします。  

2. 開発環境boxのインポート

  VirtualBoxを起動し、別途配布されたboxをインポートします。  
  boxにはすでに以下がインストールされています。
  - ruby 2.2
  - apache 2.4
  - mysql 5.6
  - samba
  - Heroku Toolbelt

## ゲストマシンへのアクセス方法

ゲストマシンを起動し、以下の方法でアクセスできるか確認しましょう。

#### SSH

1. Teratermのインストール

  WindowsからゲストマシンにSSH接続する場合、**Teraterm**というターミナルアプリを使います。

2. ゲストマシンへ接続する

  - host: ホストのIPアドレス
    > WindowsのIPアドレスは、コマンドプロンプトで<code>ipconfig</code>を実行することで確認できます。
  - ユーザー: ubuntu
  - パスワード: ______
  - ポート: 2222


  #### samba

  エクスプローラーで<code>¥¥192.168.56.101</code>を開きます。

  #### ブラウザ

  Chromeを起動し、<code>http://192.68.56.101:8080/</code>にアクセスしてみましょう。


## ゲストマシンの設定

1. プロキシ設定

  /etc/cntlm.confに自分の社内アカウントを設定します。

  ```
  $ sudo vi /etc/cntlm.conf

  Username        アカウント
  Domain          ドメイン名
  Password        パスワード

  ```

  cntlmを再起動します。
  ```
  $ sudo /etc/init.d/cntlm restart
  ```
