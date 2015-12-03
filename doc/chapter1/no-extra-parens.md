### 避免多余的括号
规则名: no-extra-parens

规则解释:
以下两种情况冗余的括号是被允许的

* 正则表达式字面量: `(/abc/).test(var)`
* 自执行函数: `var x = (function () {})(); `, `((function foo() {return 1})())`

规则选项:

* `"all"`: 默认值, 检查所有表达式
* `"functions`: 只检查函数表达式


```js
/*eslint no-extra-parens: 2*/

a = (b * c); /*error Gratuitous parentheses around expression.*/

(a * b) + c; /*error Gratuitous parentheses around expression.*/

typeof (a);  /*error Gratuitous parentheses around expression.*/

```


```js
/*eslint no-extra-parens: [2, "functions"]*/

((function foo() {}))();           /*error Gratuitous parentheses around expression.*/

var y = (function () {return 1;}); /*error Gratuitous parentheses around expression.*/

```

[源地址](http://eslint.org/docs/rules/no-extra-parens)