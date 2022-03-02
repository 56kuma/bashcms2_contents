---
Keywords: Python, Regex, 正規表現
Copyright: (C) 2022 T.Masuda
---
## 目的

* 1文字以上かつ、半角英数時

## ソース
```
import re

def isHalfWidthNumber(target):
    return True if re.fullmatch('[0-9]+', str(target)) else False

isHalfWidthNumber('123')
```

## 補足

* 正規表現
  * [0-9] … 任意の数値
  * + … 直前の文字を１回以上繰り返す。



