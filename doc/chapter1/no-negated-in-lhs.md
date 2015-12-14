### 在in操作符左侧禁用!
规则名: no-negated-in-lhs

规则解释: 这是一个典型的潜在错误

当一个开发者想要写:

```js
if (!(a in b)) {
    // do something
}
```

他们很可能写成:

```js
if (!a in b) {
    //do something
}
```

然而如果想要以上这段代码的按设想运行, 左侧的操作数应该显式的转换成字符串, 如下:

```js
if (('' + !a) in b) {
    // do  something
}
```


以下代码会被当作错误:
```js
/*eslint no-negated-in-lhs: 2*/

if(!a in b) {       /*error The `in` expression's left operand is negated*/
    // do something
}
```
