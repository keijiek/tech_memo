# mariadb 関連

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

重要な質問と回答

```shell
Remove anonymous users? [Y/n] y # anonymous user は消せ。
Disallow root login remotely? [Y/n] y # リモートで root にログインさせるな。
Remove test database and access to it? [Y/n] y # test database は消せ。
Reload privilege tables now? [Y/n] y
```

### 1.3. mycli の使用 (if you need)

```shell
sudo apt install mycli
```

---

## 2. ログイン

### 2.1. ノーマルにログイン

```shell
# パスワードつきのログイン
mysql -u root -p
mysql -u ユーザー名 -p
# linux の root user による強制ログイン
sudo mariadb
```

### 2.2. mycli でログイン

```shell
# 文法
mycli -u ユーザー名 -p パスワード
# 例
mycli -u root -p hogehoge
mycli -u fuga -p hogehoge
# linux の root user による強制ログイン
sudo mycli
```

---

## 3. ユーザー操作

### 3.1. ユーザー作成

```SQL
# ユーザー作成(ユーザー名とパスワードが合っていても、ホストが異なると認証に失敗する)
CREATE USER 'ユーザー名'@'ホスト' IDENTIFIED BY 'パスワード';
# 同名ユーザーを作らないために if not exists を入れる。
CREATE USER IF NOT EXISTS 'ユーザー名'@'ホスト' IDENTIFIED BY 'パスワード';
# 例
CREATE USER 'user01'@'localhost' IDENTIFIED BY 'hogehoge';
# 確認
SELECT user, host FROM mysql.user;
# ユーザー削除
DROP USER IF EXISTS 'ユーザー名'@'ホスト';
DROP USER IF EXISTS 'ユーザー名'@'ホスト', 'ユーザー名'@'ホスト', 'ユーザー名'@'ホスト';
```

### 3.2. ユーザーに権限付与

```SQL
# 文法
GRANT 権限のあるコマンド(カンマ区切りで複数入力) ON データベース.テーブル TO 'ユーザー'@'ホスト'
# 例: データベースを制限。その中のテーブルは制限なし。
GRANT ALL PRIVILEGES ON db_name.* TO username@localhost;
GRANT select ON db_name.* TO username@localhost;
# 例: データベースもテーブルも制限。
GRANT ALL PRIVILEGES ON db_name.table_name TO username;
# 確認
SHOW GRANTS FOR 'ユーザー'@'ホスト';
# 剥奪 (全権限, およびGRANT権限を剥奪)
REVOKE ALL PRIVILEGES, GRANT OPTION FROM 'ユーザー'@'ホスト';
```
