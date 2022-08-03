---
Keywords: Linux, Ubuntu, Command, コマンド
Copyright: (C) 2022 T.Masuda
---
# SCPコマンドの使い方

### 目次
- [SCPコマンドの使い方](#scpコマンドの使い方)
    - [目次](#目次)
    - [1. 概要](#1-概要)
    - [2.参考サイト](#2参考サイト)
    - [3.コマンド例](#3コマンド例)


### 1. 概要
* scpコマンドにて、レンタルサーバ（Linux）上にあるファイルを、ホストPC（WSL2）へコピー

### 2.参考サイト
* https://docs.docker.jp/v19.03/machine/reference/scp.html

### 3.コマンド例
* 前提条件
  * sshコマンドで、コピー元のPCへアクセスできる状態であること。

* コピー元
  * レンタルサーバ先のホスト名IP/アドレス -> hoge@153.126.182.197
  * コピー対象ファイル -> ~/work/hoge.md 
* コピー先
  * カレントディレクトリ -> 

```/bin/bash
# 実行コマンド
scp hoge@153.126.182.197:~/work/hoge.md ./
< hoge.md
```
