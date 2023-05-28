# wordpress

## 導入

```shell
# ダウンロードファイルを置きたいところへ
cd hogehoge 
# ダウンロード
wget https://ja.wordpress.org/latest-ja.tar.gz
# 展開。-C の後に、展開先のパスを記述
tar -zxvf latest-ja.tar.gz -C /var/www/html/ # このCのパスは任意
```

## パーミッションの設定

### 目的

- コンパネ上の更新が、ftpを聞かれずスムーズに行われる。(www-data のパーミッション)
- 必要なファイル編集(themes/customThemeDirへのscp等)は問題なくできる。 (自分のパーミッション)

### 必要な作業

```shell
cd /var/www/ # wordpress の祖父, document root の親, どちらが有効だったのかは不明。
sudo chown -R www-data:myUser ./dmain.com/
sudo find ./domain.com/ -type -d -exec chmod 775 {} +
sudo find ./domain.com/ -type -f -exec chmod 664 {} +
# 細かいパーミッション設定
cd ./domain.com/wordpress/
sudo chmod 660 wp-config.php
sudo chmod 660 .htaccess 
```
