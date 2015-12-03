### 避免冗余的布尔转换
规则名: no-extra-boolean-cast

规则解释: 在一些上下文中如if语句的条件里, js会自动转换成布尔值. 此时,利用!!进行布尔值转换是没有必要的.

以下的会当作错误：
```js
/*eslint no-extra-boolean-cast: 2*/

var foo = !!!bar;             /*error Redundant multiple negation.*/

var foo = !!bar ? baz : bat;  /*error Redundant double negation in a ternary condition.*/

var foo = Boolean(!!bar);     /*error Redundant double negation in call to Boolean().*/

var foo = new Boolean(!!bar); /*error Redundant double negation in Boolean constructor call.*/

if (!!foo) {                  /*error Redundant double negation in an if statement condition.*/
    // ...
}

while (!!foo) {               /*error Redundant double negation in a while loop condition.*/
    // ...
}

do {
    // ...
} while (!!foo);              /*error Redundant double negation in a do while loop condition.*/

for (; !!foo; ) {             /*error Redundant double negation in a for loop condition.*/
    // ...
}
```

[源地址](http://eslint.org/docs/rules/no-extra-boolean-cast)