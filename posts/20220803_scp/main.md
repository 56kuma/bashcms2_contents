---
Keywords: Linux, Ubuntu, Command, コマンド, bash, 変数展開
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
* bashの機能で連番のファイル名を作成
* 変数展開（シーケンス展開）という機能を使っているそうだ

### 2.参考サイト
* https://www.linuxjournal.com/content/bash-brace-expansion

### 3.コマンド例

```/bin/bash
# 実行コマンド
echo {01..10}
> 01 02 03 04 05 06 07 08 09 10

echo {a..f}
> a b c d e f

touch {a..f}.csv
ls
> a.csv  b.csv  c.csv  d.csv  e.csv  f.csv> 
```
