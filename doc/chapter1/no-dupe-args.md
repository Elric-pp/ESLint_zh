### 禁止参数重名
规则名: no-dups-args

规则解释: 一个函数的多个参数如果有重名的情况将会取第一个参数的值.在严格模式下, 将会报`SyntacError`.该规则避免该错误

```js
 /*eslint no-dupe-args: 2*/

function foo(a, b, a) {               /*error Duplicate param 'a'.*/
    console.log("which a is it?", a);
}
```

[源地址](http://eslint.org/docs/rules/no-dupe-args)