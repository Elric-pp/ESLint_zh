### 逗号结尾
规则名: comma-dangle

规则解释: 对于对象或者数组声明最后一个属性的逗号的规则

规则选项:

* `"always"`  始终需要结尾的逗号
* `"always-multiline"` 仅当单行格式书写多个属性时省略结尾的逗号
* `"never"`(默认)  不允许结尾的逗号
<br/>
<br/>

```js
/*eslint comma-dangle: [2, "always"]*/

var foo = {
    bar: "baz",
    qux: "quux"   /*error Missing trailing comma.*/
};

var arr = [1,2];  /*error Missing trailing comma.*/

foo({
  bar: "baz",
  qux: "quux"     /*error Missing trailing comma.*/
});
```



```js
/*eslint comma-dangle: [2, "always-miltiline"]*/

var foo = {
    bar: "baz",
    qux: "quux"                         /*error Missing trailing comma.*/
};

var foo = { bar: "baz", qux: "quux", }; /*error Unexpected trailing comma.*/

var arr = [1,2,];                       /*error Unexpected trailing comma.*/

var arr = [1,
    2,];                                /*error Unexpected trailing comma.*/

var arr = [
    1,
    2                                   /*error Missing trailing comma.*/
];

foo({
  bar: "baz",
  qux: "quux"                           /*error Missing trailing comma.*/
});
```


```js
/*eslint comma-dangle: [2, "never"]*/

var foo = {
    bar: "baz",
    qux: "quux",   /*error Unexpected trailing comma.*/
};

var arr = [1,2,];  /*error Unexpected trailing comma.*/

foo({
  bar: "baz",
  qux: "quux",     /*error Unexpected trailing comma.*/
});

```


[源地址](http://eslint.org/docs/rules/comma-dangle)