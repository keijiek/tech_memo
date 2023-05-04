# 技術メモ

## SQL

```shell
# 前提となる環境
$ cat /etc/lsb-release
DISTRIB_ID=Ubuntu
DISTRIB_RELEASE=22.04
DISTRIB_CODENAME=jammy
DISTRIB_DESCRIPTION="Ubuntu 22.04.2 LTS"
```

### インストール(ubuntu)

```shell
sudo apt update && sudo apt upgrade -y
sudo apt install mariadb-client mariadb-server
```
