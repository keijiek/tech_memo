# apache2

## install


## 事前のコンフィグテスト

```shell
sudo apache2ctl configtest
```

## php-fpm を有効化

```shell
sudo a2enmod proxy_fcgi setenvif
sudo a2enconf php8.1-fpm
sudo systemctl restart php8.1-fpm apache2
# sudo systemctl reload apache2
# 確認
sudo systemctl status php8.1-fpm.service
sudo systemctl status apache2.service
```

### php-fpm をインストールした時のメッセージ
```
NOTICE: Not enabling PHP 8.1 FPM by default.
NOTICE: To enable PHP 8.1 FPM in Apache2 do:
NOTICE: a2enmod proxy_fcgi setenvif
NOTICE: a2enconf php8.1-fpm
NOTICE: You are seeing this message because you have apache2 package installed.
```
