### 常量作条件
规则名: no-constant-conditione

以下的会当作错误：
```js
/*eslint no-constant-condition: 2*/

if (true) {             /*error Unexpected constant condition.*/
    doSomething();
}

var result = 0 ? a : b; /*error Unexpected constant condition.*/

while (-2) {            /*error Unexpected constant condition.*/
    doSomething();
}

for (;true;) {          /*error Unexpected constant condition.*/
    doSomething();
}

do{                     /*error Unexpected constant condition.*/
    something();
} while (x = -1)
```

[源地址](http://eslint.org/docs/rules/no-constant-condition)