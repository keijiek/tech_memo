# php

## とりあえず php をインストール

```shell
sudo apt install php 
```

## モジュール確認

次のコマンドで足りないモジュールを確認しながらインストール。

```shell
php -m
# または
php -m | grep モジュール名
```

## phpinfo()

下記で出力される info.php をウェブブラウザで見ると、詳しい状態が分かる。

```shell
cd hogehoge # ウェブサーバーで公開されている任意の場所
echo '<?php phpinfo(); ?>' > info.php
```


## WordPress に必要なモジュール一覧
[Server Environment](https://make.wordpress.org/hosting/handbook/server-environment/#php-extensions)

- json
- curl
- dom (php-xml で一緒に入る)
- exif
- fileinfo
- hash
- imagick
- mbstring
- openssl
- pcre
- xml
- zip

## wordpress 用に追加すべきモジュール

- php-curl
- php-mbstring
- php-imagick
  - ImageMagick 
  - Ghost Script
- php-xml
- php-zip
- php-mysql

```bash
sudo apt install php-curl php-mbstring php-imagick php-xml php-zip php-mysql
```

## wordpress 取得と展開

```shell

```
