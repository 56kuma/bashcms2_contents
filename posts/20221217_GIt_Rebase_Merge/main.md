---
Keywords: Git, Command, Rebase, Merge
Copyright: (C) 2022 T.Masuda
---
# DevelopブランチにMainブランチを取り込む（merge,rebase)

### 目次
- [DevelopブランチにMainブランチを取り込む（merge,rebase)](#developブランチにmainブランチを取り込むmergerebase)
    - [目次](#目次)
    - [1. 概要](#1-概要)
    - [2. Developブランチマージ前](#2-developブランチマージ前)
    - [3. merge実行時](#3-merge実行時)
    - [4. rebase実行時](#4-rebase実行時)
    - [5. 参考書籍](#5-参考書籍)


### 1. 概要
* [git-flow](https://nvie.com/posts/a-successful-git-branching-model/)において、Developブランチ作成当時よりも進んでしまったmainブランチのコミットを、Developブランチに取り込む時の挙動を確認したい。
* 取り込む際の手段として、```merge / rebase``` の２パターンが考えられ、各々の違いを知るのが目的。

### 2. Developブランチマージ前
<div class="mermaid">
%%{init: { 'logLevel': 'debug', 'theme': 'base', 'gitGraph': {'showBranches': true, 'showCommitLabel':true,'mainBranchName': 'Main'}} }%%
      gitGraph
        commit id:"Release 221203"
        commit id:"Release 221210"
        branch Develop
        commit id:"add) Instagram Button"
        checkout Main
        commit id:"Release 221217"
        checkout Develop
        commit id:"refactor) Button Name"
</div>

### 3. merge実行時
* これまでのDevelopブランチのコミットIDは ```維持（変わらない）``` 。

<div class="mermaid">
%%{init: { 'logLevel': 'debug', 'theme': 'base', 'gitGraph': {'showBranches': true, 'showCommitLabel':true,'mainBranchName': 'Main'}} }%%
      gitGraph
        commit id:"Release 221203"
        commit id:"Release 221210"
        branch Develop
        commit id:"add) Instagram Button"
        checkout Main
        commit id:"Release 221217"
        checkout Develop
        commit id:"refactor) Button Name"
        merge Main
</div>

### 4. rebase実行時
* これまでのDevelopブランチのコミットIDは ```変更（新しく採番される）``` 。

<div class="mermaid">
%%{init: { 'logLevel': 'debug', 'theme': 'base', 'gitGraph': {'showBranches': true, 'showCommitLabel':true,'mainBranchName': 'Main'}} }%%
      gitGraph
        commit id:"Release 221203"
        commit id:"Release 221210"
        commit id:"Release 221217"
        branch Develop
        commit id:"add) Instagram Button **"
        checkout Develop
        commit id:"refactor) Button Name **"
</div>

### 5. 参考書籍
* [改訂2版 わかばちゃんと学ぶ Git使い方入門 Kindle版](https://www.amazon.co.jp/%E6%94%B9%E8%A8%822%E7%89%88-%E3%82%8F%E3%81%8B%E3%81%B0%E3%81%A1%E3%82%83%E3%82%93%E3%81%A8%E5%AD%A6%E3%81%B6-Git%E4%BD%BF%E3%81%84%E6%96%B9%E5%85%A5%E9%96%80-%E6%B9%8A%E5%B7%9D%E3%81%82%E3%81%84-ebook/dp/B096TH798S/ref=sr_1_1?__mk_ja_JP=%E3%82%AB%E3%82%BF%E3%82%AB%E3%83%8A&crid=1OEP59IF8OEW0&keywords=git+%E3%82%8F%E3%81%8B%E3%81%B0&qid=1671272425&sprefix=git+%E3%82%8F%E3%81%8B%E3%81%B0%2Caps%2C174&sr=8-1)
