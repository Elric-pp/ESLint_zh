### 正则表达式中不允许空字符范围
规则名: no-empty-character-class

规则解释: 正则表达式中如果使用空的字符范围[]会导致不可预见的错误

```js
/*eslint no-empty-character-class: 2*/

var foo = /^abc[]/;  /*error Empty class.*/

/^abc[]/.test(foo);  /*error Empty class.*/

bar.match(/^abc[]/); /*error Empty class.*/
```

[源地址](http://eslint.org/docs/rules/no-empty-character-class)
