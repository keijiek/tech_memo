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

### 1.1. インストール

```shell
sudo apt update && sudo apt upgrade -y
sudo apt install mariadb-client mariadb-server
```

### 1.2. 初回起動

```shell
sudo mysql_secure_installation
```

### 1.3. mycli の使用 (if you need)

mariadb や mysql をコマンドラインで操作するためのツール。入力補完や色付きで操作しやすくなる。

#### 1.3.0 詳細確認(if you need)

```shell
apt show mycli
```

#### 1.3.1. mycli をインストール

```shell
sudo apt install mycli
```

#### 1.3.2. mycli でログイン

```shell
# 文法
mycli -u ユーザー名 -p パスワード
# 例
mycli -u root -p hogehoge
mycli -u fuga -p hogehoge
```

---

## 2. ログイン

### 2.1. sudo で無理やりログイン

```shell
sudo mariadb
```

### 2.2. 特定ユーザーにパスワードを使ってログイン

```shell
mysql -u root -p
mysql -u ユーザー名 -p
```

---

## 3. ユーザー操作

```shell
# ユーザー作成
```
