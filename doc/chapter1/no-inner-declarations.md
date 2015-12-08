### 禁止在块语句中声明

规则名称: no-inner-declarations

规则解释:

* 在ES6中, 由于解释器有时候会错误的跨越作用域去接受一个函数, 所以函数声明仅允许在程序或者另一个函数体的第一层;
* 正确的函数表达式或者匿名函数不受此规则影响
* 为了代码更加易读, 变量的声明放在前面是一个好习惯
* let 和 const 关键字带有作用域绑定的作用,所以也不受此规则的影响


规则选项:

* `"both"` 同时检测函数和变量声明, 默认只检测函数声明

```js
/*eslint no-inner-declarations: 2*/

if (test) {
    function doSomething() { }        /*error Move function declaration to program root.*/
}

function doSomethingElse() {
    if (test) {
        function doAnotherThing() { } /*error Move function declaration to function body root.*/
    }
}
```


```js
/*eslint no-inner-declarations: [2, "both"]*/

if (test) {
    var foo = 42;            /*error Move variable declaration to program root.*/
}

function doAnotherThing() {
    if (test) {
        var bar = 81;        /*error Move variable declaration to function body root.*/
    }
}
```


禁用场景:

* 该规则会保留到函数的块级作用域正式在ES6中实现, 不过到了那时, 应该成为强制规则了
* 当你已经运用了`"block-scoped-var"`规则时, 或者尽管有变量提升, 在嵌套作用域中声明变量不会造成影响, 应该禁用掉变量检查



[源地址](http://eslint.org/docs/rules/no-inner-declarations)