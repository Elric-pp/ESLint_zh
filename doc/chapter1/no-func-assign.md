### 禁止给函数赋值
规则名: no-func-assign

规则解释: 定义函数的方式有函数表达式和函数声明两种, 赋值或者重写函数一般是失误

```js
/*eslint no-func-assign: 2*/

function foo() {}
foo = bar;        /*error 'foo' is a function.*/

function foo() {
    foo = bar;    /*error 'foo' is a function.*/
}
```

[源地址](http://eslint.org/docs/rules/no-func-assign)