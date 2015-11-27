### 在正则表达式中禁用控制字符

规则名: no-control-regex

规则解释: [控制字符](https://zh.wikipedia.org/wiki/%E6%8E%A7%E5%88%B6%E5%AD%97%E7%AC%A6)

以下的会当作错误：
```js
/*eslint no-control-regex: 2*/

var pattern1 = /\\x1f/;
var pattern2 = new RegExp("\x1f"); /*error Unexpected control character in regular expression.*/
```

[源地址](http://eslint.org/docs/rules/no-control-regex)