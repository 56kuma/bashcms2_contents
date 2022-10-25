---
Keywords: WSL2, Ubuntu, Python, pip, pip3
Copyright: (C) 2022 T.Masuda
---
# WSL2でpip3のインストール

### 目次
- [WSL2でpip3のインストール](#wsl2でpip3のインストール)
    - [目次](#目次)
    - [1.概要](#1概要)
    - [2.発生したエラー](#2発生したエラー)
    - [3.実施コマンド](#3実施コマンド)


### 1.概要
* WSL2を起動後、pip3のインストールをしたらエラーが出た
* 先に sudo apt update をすることで解決

### 2.発生したエラー
```cmd
… 
E: Failed to fetch http://security.ubuntu.com/ubuntu/pool/main/p/python3.8/libpython3.8-dev_3.8.10-0ubuntu1~20.04.4_amd64.deb  404  Not Found [IP: 185.125.190.36 80]
E: Failed to fetch http://security.ubuntu.com/ubuntu/pool/main/p/python3.8/python3.8-dev_3.8.10-0ubuntu1~20.04.4_amd64.deb  404  Not Found [IP: 185.125.190.36 80]
E: Unable to fetch some archives, maybe run apt-get update or try with --fix-missing?
```

### 3.実施コマンド

```/bin/bash
sudo apt update
sudo apt install python3-pip
```
