# 文档
mapKeysDeepLodash 主要用于深度遍历对象的 key 并通过回调函数对对象进行处理，是 lodash 的 mapKeys 的增强版。

## 函数参数

- param {object} obj 待遍历的对象
- param {(value, key) => string} callback 回调函数对函数进行处理
- return {object} 处理后的对象

举个例子（要包含代码用例）

```js
const mapKeysDeep = require("map-keys-deep-lodash");

mapKeysDeep({a: "b", c: "d", e: {c: "f", g: {c: "h"}}}, (value, key) => {
  if (key === "c") {
    return "zzz";
  }

  return key;
});
//=> {a: "b", zzz: "d", e: {zzz: "f", g: {zzz: "h"}}}
```

特殊说明，比如特殊情况下会报错等
