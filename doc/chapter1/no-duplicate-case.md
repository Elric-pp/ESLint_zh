### 禁止重复条件
规则名: no-duplicate-case

规则解释: 在switch语句中禁止出现重复case

```js
/*eslint no-duplicate-case: 2*/

var a = 1,
    one = 1;

switch (a) {
    case 1:
        break;
    case 1:      /*error Duplicate case label.*/
        break;
    case 2:
        break;
    default:
        break;
}

```

[源地址](http://eslint.org/docs/rules/no-duplicate-case)