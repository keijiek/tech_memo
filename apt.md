# apt

## 言わずもがなの機能

```shell
sudo apt update && apt list --upgradable && sudo apt upgrade -y
```

---

## パッケージ検索や、詳細の表示

### パッケージを検索

```shell
apt search 検索ワード
```

なお、`apt list 検索ワード` で、検索ワードと名前が完全に一致するパッケージの一覧を表示する。


### パッケージ単体の詳細

```shell
apt show パッケージ名
```

---
