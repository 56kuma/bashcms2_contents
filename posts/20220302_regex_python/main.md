---
Keywords: Python, Regex, 正規表現
Copyright: (C) 2022 T.Masuda
---
## 目的

* 正規表現にて、半角数値かつ1文字以上の条件に合致する構文

## ソース
```
import re

def isHalfWidthNumber(target):
    return True if re.fullmatch('[0-9]+', str(target)) else False

isHalfWidthNumber('123')
```

## 補足

* 正規表現
  * [0-9] … 任意の半角数値
  * \+ … 直前の文字を１回以上繰り返す。

## こんな時どーする？

* 半角数値では無く、全角数値とする場合
  * [0-9] の代わりに [０-９]

## 参考

[https://docs.python.org/3/library/re.html#re.fullmatch](https://docs.python.org/3/library/re.html#re.fullmatch)
