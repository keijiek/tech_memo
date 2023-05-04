# mariadb 関連

## 目次
1. インストール

## 前提となる環境

```shell
$ cat /etc/lsb-release
DISTRIB_ID=Ubuntu
DISTRIB_RELEASE=22.04
DISTRIB_CODENAME=jammy
DISTRIB_DESCRIPTION="Ubuntu 22.04.2 LTS"
```

## 1. インストール(ubuntu)

```shell
sudo apt update && sudo apt upgrade -y
sudo apt install mariadb-client mariadb-server
```

## 2. 初回起動

```shell
sudo mysql_secure_installation
```

## 3. ログイン

```shell
# sudo で無理やりログイン
sudo mariadb

# root でパスワードを入力してログイン
mysql -u root -p

# ユーザーでログイン
mysql -u ユーザー名 -p
```

## 4. ユーザー操作

```shell
# ユーザー作成
```
