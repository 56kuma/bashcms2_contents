---
Keywords: Linux, Ubuntu, Python, venv
Copyright: (C) 2022 T.Masuda
---
# Ubuntu 22.04 に venv

## 参考
* https://hirooka.pro/python-venv-ubuntu-20-04/
* https://www.nemotos.net/?p=4502

## 概要
Ubuntu22.04にPython仮想環境「venv」を設定した時のメモ。

## 目次
1. Python のバージョン確認
2. pip インストール
3. venvのインストール

## 1. Python のバージョン確認
``` cmd
<!-- python2 は無かった -->
which python2

<!-- python3 はあった -->
which python3
> /usr/bin/python3

python3 --version
> python 3.10.4
```

## 2. pip インストール 
* pipがインストールされていなければインストール

``` cmd
<!-- インストールされていない場合 -->
pip
> コマンド 'pip' が見つかりません。次の方法でインストールできます:
> sudo apt install python3-pip

<!-- pip3のインストール -->
sudo apt install python3-pip

<!-- インストールされているか確認 -->
which pip3
> /usr/bin/pip3
```

## 3. venv インストール
* python3-venv パッケージをインストールし仮想環境を作成

``` cmd
<!-- python3-venv パッケージのインストール -->
sudo apt install -y python3-venv

<!-- ホームディレクトリ直下「python」にdevという仮想環境を作成 -->
python3 -m venv ~/python/dev

<!-- venv環境に入る -->
source ~/python/dev/bin/activate

<!-- venv環境から抜ける -->
deactivate
```

