Wordpress 自作テンプレート開発環境
====

Wordpress の自作テンプレートを開発する環境を構築します。

### ディレクトリ構造
```
.
├── docker （各種Daemon）
│   │
│   ├── apache （Webサーバー）
│   │   ├── conf.d (apacheの設定ファイル)
│   │   └── logs （apacheのログ）
│   ├── mysql （DBサーバー）
│   │   ├── conf.d (mysqlの設定ファイル)
│   │   ├── data (mysqlのデータファイル)
│   │   ├── init （mysqlの初期DDL）
│   │   ├── logs （mysqlのログ）
│   │   └── script （mysql関連のスクリプト）
│   ├── php （PHP-FRM）
│   │   └── logs （phpのログ）
│   └── phpmyadmin （DB管理ツール）
│
├── public （公開ディレクトリ）
├── dc.sh （Dockerの起動用スクリプト）
└── src （自作テンプレート）
```

## Description

## Demo

## VS. 

## Requirement

## Usage

```
# サーバーを起動する
$ ./dc.sh start

# データベースが立ち上がるまで少し待ちます。(1分程度)

# ブラウザでアクセス
$ open http://localhost/
```

### 初回アクセス時にデータベース接続が尋ねられるので以下で入力してください。
```
データベース名：wordpress
ユーザー名：root 
パスワード名：password
データベースのホスト名：mysql
```

### サーバーを停止する場合
```
$ ./dc.sh stop
```

### データベースを参照したい場合
phpmyadmin でデータベースを管理できます。

http://localhost:8888/

## Install

```
# WSLにphp5系をインストール
sudo apt-get install software-properties-common python-software-properties
sudo apt-get update
sudo apt-get upgrade

sudo add-apt-repository ppa:ondrej/php
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install php5.6 
sudo apt-get install php5.6-xml
sudo apt-get install php5.6-phalcon



# Dockerイメージを初期化する
$ ./dc.sh init

# Dockerイメージを作成して起動する
$ ./dc.sh start

```

## Contribution

## Licence

[MIT](https://github.com/isystk/docker-wordpress/LICENCE)

## Author

[isystk](https://github.com/isystk)


