---
Keywords: C++, オブジェクト指向, コンパイル
Copyright: (C) 2022 T.Masuda
---
# C++でhppファイルをコンパイルする方法

### 目次
- [C++でhppファイルをコンパイルする方法](#cでhppファイルをコンパイルする方法)
    - [目次](#目次)
    - [1. 概要](#1-概要)
    - [2. サンプルファイル各々の関係](#2-サンプルファイル各々の関係)
    - [3. サンプルソース](#3-サンプルソース)
    - [4. コンパイル](#4-コンパイル)
    - [5. 実行コマンド \& 結果](#5-実行コマンド--結果)


### 1. 概要
* C++において、hppファイルの在り方とコンパイル方法を記載
* main.cpp が起動ファイル、かつ check.cpp / check.hpp を読み込んでいるとしたら、各ファイルの関係を知るのが目的

### 2. サンプルファイル各々の関係
* 矢印先が include しているファイルとなる。

<div class="mermaid">
  graph TB;
  main.cpp --> check.hpp;
  check.cpp --> check.hpp;
</div>

### 3. サンプルソース
* check.hpp

``` c++
#include <string>
#include <iostream>

class Check {
    public:
        // メンバー定数
        static const std::string CAMERA_NAME;
        static const int CAMERA_NO;
        static const double CAMERA_PREFIX;
        // メンバー変数
        std::string DESCRIPTION;
        // 静的メソッド
        static void displayInt(int displayInt);
        static void displayStr(const std::string &displayStr);
};

```

* check.cpp

``` c++
#include <iostream>
#include "./check.hpp"

// 定数への値設定
const std::string Check::CAMERA_NAME = "fuga";
const int Check::CAMERA_NO = 123;
const double Check::CAMERA_PREFIX = 111;

// not static変数はクラス外で定義できない
// std::string Check::DESCRIPTION = "Sell Item";

void Check::displayInt(int displayInt){
    std::cout << "displayInt:\t" << displayInt << std::endl;
};

void Check::displayStr(const std::string &displayStr){
    std::cout << "displayStr:\t" << displayStr << std::endl;
};

```

* main.hpp

``` c++
#include "check.hpp"
int main(){

  Check ch;
  ch.DESCRIPTION = "Discount Item.";

  std::cout << "--- start ---" << std::endl;
  // static const へのアクセス
  std::cout << Check::CAMERA_NAME << std::endl;
  std::cout << Check::CAMERA_NO << std::endl;
  std::cout << Check::CAMERA_PREFIX << std::endl;

  std::cout << "--- static method ---" << std::endl;
  Check::displayInt(123);
  Check::displayStr(ch.DESCRIPTION);

};

```

### 4. コンパイル
* 登場した3ファイルが c:\sample に格納されていることを前提
* -o … 出力ファイルの名前を指定できる、今回は"hoge"が出力
* .hppはコンパイルしなくてもOK

```cmd
cd c:\sample
g++ -std=c++17 -o hoge main.cpp check.cpp
```

### 5. 実行コマンド & 結果
```cmd

cd c:\sample
./hoge

> --- start ---
> fuga
> 123
> 111
> --- static method ---
> displayInt:     123
> displayStr:     Discount Item.

```
