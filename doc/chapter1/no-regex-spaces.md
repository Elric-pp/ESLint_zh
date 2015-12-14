### 正则中禁用多个空格
规则名称: no-regex-spaces

规则解释: 正则表达式有些时候非常复杂, 难以理解, 所以尽可能的保持其简单可以有效的避免错误. 使用多个空格是其中一个非常容易出错的地方;

例如:
```js
var re = /foo   bar/;
```

上面的正则很难一眼分辨到底要匹配多少个空格, 所以, 更好的写法应该是标明匹配多少个空格, 如下


```js
var re = /foo {3}bar/;
```


```js
var re = /foo   bar/; /*error Spaces are hard to count. Use {3}.*/
```

[源地址](http://eslint.org/docs/rules/no-regex-spaces)