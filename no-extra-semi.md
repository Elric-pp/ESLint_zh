### 避免多余的分号
规则名: no-extra-semi

规则解释: js解释器会自动的添加分号, 所以, 书写错误或者不清楚哪里需要添加分号会导致多余的分号


```js
/*eslint no-extra-semi: 2*/

var x = 5;;      /*error Unnecessary semicolon.*/

function foo() {
    // code
};               /*error Unnecessary semicolon.*/

```

[源地址](http://eslint.org/docs/rules/no-extra-semi)