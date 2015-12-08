### 避免多余的分号
规则名称: no-extra-semi

规则解释: 由于对js什么时候会自动的添加分号的不了解, 导致很容易不小心造成了多余的分号

```js
/*eslint no-extra-semi: 2*/

var x = 5;;      /*error Unnecessary semicolon.*/

function foo() {
    // code
};               /*error Unnecessary semicolon.*/
```

[源地址](http://eslint.org/docs/rules/no-extra-semi)