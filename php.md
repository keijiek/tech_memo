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
