### 块语句内容不能为空
规则名: no-empty

规则解释: 块语句内容为空通常是一个疏漏

```js
/*eslint no-empty: 2*/

if (foo) {         /*error Empty block statement.*/
}

while (foo) {      /*error Empty block statement.*/
}

switch(foo) {      /*error Empty switch statement.*/
}

try {
    doSomething();
} catch(ex) {      /*error Empty block statement.*/

} finally {        /*error Empty block statement.*/

}
```

[源地址](http://eslint.org/docs/rules/no-empty)