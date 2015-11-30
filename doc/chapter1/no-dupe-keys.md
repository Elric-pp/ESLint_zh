### 禁止键名重复
规则名: no-dupe-keys

规则解释: 避免在对象中使用重复的键名导致的错误

```js
/*eslint no-dupe-keys: 2*/

var foo = {
    bar: "baz",
    bar: "qux"     /*error Duplicate key 'bar'.*/
};

var foo = {
    "bar": "baz",
    bar: "qux"     /*error Duplicate key 'bar'.*/
};

var foo = {
    0x1: "baz",
    1: "qux"       /*error Duplicate key '1'.*/
};
```