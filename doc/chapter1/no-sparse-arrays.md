### 禁用稀疏数组
规则名称: no-sparse-arrays

规则解释: 稀疏数组容易使其他人迷惑, 到底是故意的代码还是书写错误, 所以避免使用稀疏数组除非你确信它有用处;

```js
 /*eslint no-sparse-arrays: 2*/

var items = [,];                 /*error Unexpected comma in middle of array.*/
var colors = [ "red",, "blue" ]; /*error Unexpected comma in middle of array.*/
```

[源地址](http://eslint.org/docs/rules/no-sparse-arrays)