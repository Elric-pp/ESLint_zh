### 禁用不规则的空格
规则名: no-irregular-whitespace

规则解释: 无效或者不规则的空格会导致 ECMAScirpt 5 解释器出现问题,  同时也导致了代码的可维护性大大降低, 就像混用 `tab` 和 `space` 一样

> 已知的问题有:
 * 零宽空格
    + 解释器不会把它单做分隔符, 报`Unexpected token ILLEGAL`
    + 现代浏览器不会展现它, 导致了可视化的差异
 *  换行符
    + 在JSON中使用会导致解析错误


该规则对以下字符在字符串以外的地方使用报错:
```
\u000B - Line Tabulation (\v) - <VT>
\u000C - Form Feed (\f) - <FF>
\u00A0 - No-Break Space - <NBSP>
\u0085 - Next Line
\u1680 - Ogham Space Mark
\u180E - Mongolian Vowel Separator - <MVS>
\ufeff - Zero Width No-Break Space - <BOM>
\u2000 - En Quad
\u2001 - Em Quad
\u2002 - En Space - <ENSP>
\u2003 - Em Space - <EMSP>
\u2004 - Tree-Per-Em
\u2005 - Four-Per-Em
\u2006 - Six-Per-Em
\u2007 - Figure Space
\u2008 - Punctuation Space - <PUNCSP>
\u2009 - Thin Space
\u200A - Hair Space
\u200B - Zero Width Space - <ZWSP>
\u2028 - Line Separator
\u2029 - Paragraph Separator
\u202F - Narrow No-Break Space
\u205f - Medium Mathematical Space
\u3000 - Ideographic Space
```

```js
/*eslint no-irregular-whitespace: 2*/

function thing() /*<NBSP>*/{ /*error Irregular whitespace not allowed*/
  return 'test';
}

function thing( /*<NBSP>*/){ /*error Irregular whitespace not allowed*/
  return 'test';
}

function thing /*<NBSP>*/(){ /*error Irregular whitespace not allowed*/
  return 'test';
}

function thing᠎/*<MVS>*/(){   /*error Irregular whitespace not allowed*/
  return 'test';
}

function thing() {
  return 'test'; /*<ENSP>*/  /*error Irregular whitespace not allowed*/
}

function thing() {
  return 'test'; /*<NBSP>*/  /*error Irregular whitespace not allowed*/
}
```

[源地址](http://eslint.org/docs/rules/no-irregular-whitespace)