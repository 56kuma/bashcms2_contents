---
Keywords: Linux, Ubuntu
Copyright: (C) 2022 T.Masuda
---
# CMakeとは？

### 目次

1. 概要
2. 参考サイト
3. Install
4. お作法とその確認


### 1. 概要
* CMakeLists.txt を作成し、それを あ で実行すれば解釈してMakefileやプロジェクト・ファイル（*.proj）を生成してくれる。 

### 2.参考サイト
* https://theolizer.com/theolizer/cmake_and_cmakelists/
* https://theolizer.com/cpp-school1/cpp-school1-3/#install_tools

### 3.Install
```bash
<!-- ダウンロード -->
sudo apt-get install cmake
確認コマンド
cmake --version
< cmake version 3.16.3
```

### 4.お作法
* 実行時は CMakeLists.txt と同じ階層にビルド用のフォルダ(buildなど)、を作成して実行する。build用に生成されるファイルが多く、ソース管理が面倒になる原因となるので、これらのファイルを別途フォルダを切って保存するのが吉。
* CMakeLists.txt の実行
```bash 
mkdir build
cd build
cmake ..
```
* 実行後の生成ファイル
```
.
├── CMakeCache.txt
├── CMakeFiles
│   ├── 3.16.3
│   │   ├── CMakeCCompiler.cmake
│   │   ├── CMakeCXXCompiler.cmake
│   │   ├── CMakeDetermineCompilerABI_C.bin
│   │   ├── CMakeDetermineCompilerABI_CXX.bin
│   │   ├── CMakeSystem.cmake
│   │   ├── CompilerIdC
│   │   │   ├── CMakeCCompilerId.c
│   │   │   ├── a.out
│   │   │   └── tmp
│   │   └── CompilerIdCXX
│   │       ├── CMakeCXXCompilerId.cpp
│   │       ├── a.out
│   │       └── tmp
│   ├── CMakeDirectoryInformation.cmake
│   ├── CMakeOutput.log
│   ├── CMakeTmp
│   ├── Makefile.cmake
│   ├── Makefile2
│   ├── TargetDirectories.txt
│   ├── cmake.check_cache
│   ├── hello.dir
│   │   ├── DependInfo.cmake
│   │   ├── build.make
│   │   ├── cmake_clean.cmake
│   │   ├── depend.make
│   │   ├── flags.make
│   │   ├── link.txt
│   │   └── progress.make
│   └── progress.marks
├── Makefile
└── cmake_install.cmake
```
