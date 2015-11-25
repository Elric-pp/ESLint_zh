### 禁用console
规则名: no-console
规则解释: console用于调试代码, 生产环境不应该有console

以下的会当作错误：
```js
/*eslint no-console: 2*/

console.log("Hello world!");              /*error Unexpected console statement.*/
console.error("Something bad happened."); /*error Unexpected console statement.*/
```

[源地址](http://eslint.org/docs/rules/no-console)