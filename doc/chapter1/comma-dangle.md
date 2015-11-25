### 逗号结尾
规则名: comma-dangle
> IE8不支持对象或者数组最后的一个加逗号
> 该规则强制

规则选项:


```
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