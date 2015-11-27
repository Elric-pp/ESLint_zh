### 条件中赋值
规则名: no-cond-assign

规则解释: 该规则是为了消除在 `for`, `if`, `while`, `do...while`等条件语句中进行容易引起误会的赋值

规则选项:

* `except-parens`(默认): 不允许赋值, 除了被括号包裹起来的情况
* `always`: 全部不允许赋值
<br/>

### "except-parens"

以下的会当作错误：

```js
/*eslint no-cond-assign: 2*/

var x;
if (x = 0) {         /*error Expected a conditional expression and instead saw an assignment.*/
    var b = 1;
}

function setHeight(someNode) {
    "use strict";
    do {             /*error Expected a conditional expression and instead saw an assignment.*/
        someNode.height = "100px";
    } while (someNode = someNode.parentNode);
}
```

以下的会通过检验：
```js
/*eslint no-cond-assign: 2*/

var x;
if (x === 0) {
    var b = 1;
}


function setHeight(someNode) {
    "use strict";
    do {
        someNode.height = "100px";
    } while ((someNode = someNode.parentNode) !== null);
}
```

### "always"
以下的会当作错误：
```js
/*eslint no-cond-assign: [2, "always"]*/

var x;
if (x = 0) {         /*error Unexpected assignment within an 'if' statement.*/
    var b = 1;
}

function setHeight(someNode) {
    "use strict";
    do {             /*error Unexpected assignment within a 'do...while' statement.*/
        someNode.height = "100px";
    } while (someNode = someNode.parentNode);
}

function setHeight(someNode) {
    "use strict";
    do {             /*error Unexpected assignment within a 'do...while' statement.*/
        someNode.height = "100px";
    } while ((someNode = someNode.parentNode));
}

function setHeight(someNode) {
    "use strict";
    do {             /*error Unexpected assignment within a 'do...while' statement.*/
        someNode.height = "100px";
    } while ((someNode = someNode.parentNode) !== null);
}
```


[源地址](http://eslint.org/docs/rules/no-cond-assign)