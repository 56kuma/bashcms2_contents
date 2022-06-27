---
Keywords: Git
Copyright: (C) 2021 T.Masuda
---
# Git Command

1. インストール
1. インストール後の初期設定
1. 使用頻度の高いコマンド


## 1. インストール
```Git
# Ubuntu
sudo apt update
sudo apt install git 
```

## 2. インストール後の初期設定

```Git
# ユーザ名の設定
git config --global user.name "any_name"

# メールアドレスの設定
git config --global user.email "anyu_email"

# 確認コマンド
git config --list

# 削除コマンド
git config --global --unset user.name
```

## 3. 使用頻度の高いコマンド

```Git
# 変更ファイルがあるかの確認
git status

# ブランチの切り替え
git checkout [ブランチ名]

# Staging 環境への移行
git add ./

# コミット
# -m ：message, コミットメッセージの付与
git commit

# リモートリポジトリへプッシュ
git push
```
