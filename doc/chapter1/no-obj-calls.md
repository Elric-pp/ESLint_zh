### 禁止调用内置对象
规则名称: no-obj-calls

规则解释: ECMAScript 提供了一些标准内置对象供使用, 有一些对象因为首字母大写看上去好像一个构造函数(如 `Math` 和 `Json`), 但如果你把他们当函数来调用时将会报错

```js
/*eslint no-obj-calls: 2*/

var x = Math(); /*error 'Math' is not a function.*/
var y = JSON(); /*error 'JSON' is not a function.*/
```

[源地址](http://eslint.org/docs/rules/no-obj-calls)