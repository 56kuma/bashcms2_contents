---
Keywords: Python, Map
Copyright: (C) 2022 T.Masuda
---

# Python 正規表現

### 目的

* List型で格納された文字列を、まとめてInt型に変換したい。

### ソース

```python

str_list = ['100', '200', '300']
str_list_map = list(map(int, str_list))

```

```result
> [100, 200, 300]
```

### 補足

#### map()
* 戻り値はmapオブジェクト、print(mapオブジェクト)では表示されない

### こんな時どーする？

#### List型の数値全てを合計したいときは？

```python
# sum()を使う
int_list = [100, 200, 300]
sum(int_list)
```

```result
> 600
```

### 参考

* [Official Doc（リスト型）](https://docs.python.org/ja/3/library/stdtypes.html#lists)
* [Official Doc（Map()）](https://docs.python.org/ja/3/library/functions.html#map) 
