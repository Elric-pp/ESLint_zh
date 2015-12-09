### 禁止无效的正则表达式
规则名:   no-invalid-regexp.md

规则解释: 该规则校验传给`RegExp`对象的字符串参数

```js
/*eslint no-invalid-regexp: 2*/

RegExp('[')      /*error Invalid regular expression: /[/: Unterminated character class*/

RegExp('.', 'z') /*error Invalid flags supplied to RegExp constructor 'z'*/

new RegExp('\\') /*error Invalid regular expression: /\/: \ at end of pattern*/
```


ES6新的修饰符
ECMAScript 6 添加了新的修饰符 "u"[unicode](http://es6.ruanyifeng.com/#docs/regex#u修饰符) 和 "y"[sticky](http://es6.ruanyifeng.com/#docs/regex#y修饰符), 可以添加下面的代码到`.eslintrc`中以启用它们

```
"ecmaFeatures": {
  "regexYFlag": true,
  "regexUFlag": true
}
```