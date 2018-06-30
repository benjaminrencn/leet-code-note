# <a id="validParentheses"></a>有效的括号&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.validParentheses] #

## 描述 ##

给定一个只包括 `'('`，`')'`，`'{'`，`'}'`，`'['`，`']'` 的字符串，判断字符串是否有效。

有效字符串需满足：

1. 左括号必须用相同类型的右括号闭合。
1. 左括号必须以正确的顺序闭合。

注意空字符串可被认为是有效字符串。

示例 1:

> 输入: "()"  
> 输出: true

示例 2:

> 输入: "()[]{}"  
> 输出: true

示例 3:

> 输入: "(]"  
> 输出: false

示例 4:

> 输入: "([)]"  
> 输出: false

示例 5:

> 输入: "{[]}"  
> 输出: true

## 解答 ##

去除相邻括号

`880ms` `2.47%`

```javascript
/**
 * @param {string} s
 * @return {boolean}
 */
var isValid = function(s) {
  var parentheses = {
    '(': ')',
    '{': '}',
    '[': ']'
  }
  var afterRemove;

  while (s.length !== 0) {
    afterRemove = removeParentheses(s);
    if (afterRemove === s) {
      return false;
    }
    s = afterRemove;
  }
  return true;

  function removeParentheses(str) {
    var i = 0;
    while (i < str.length - 1) {
      if (parentheses[str[i]] === str[i + 1]) {
        str = str.slice(0, i).concat(str.slice(i + 2, str.length));
      } else {
        i ++;
      }
    }
    return str;
  }
};
```

栈

`76ms` `73.73%`

```javascript
/**
 * @param {string} s
 * @return {boolean}
 */
var isValid = function(s) {
  let parentheses = {
    '(': ')',
    '{': '}',
    '[': ']'
  };
  let stack = [];
  for (var i = 0; i < s.length; i ++) {
    if (parentheses[s[i]]) {
      stack.push(s[i]);
    } else {
      if (parentheses[stack.pop()] !== s[i]) {
        return false;
      }
    }
  }
  if (stack.length > 0) {
    return false;
  } else {
    return true;
  }
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 有效的括号  
  <https://leetcode-cn.com/problems/valid-parentheses/description/>
* LeetCode problems longest-common-prefix  
  <https://leetcode.com/problems/valid-parentheses/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.validParentheses]: ../../README.md#problemSet.algorithm.validParentheses "README"
<!-- 链接 结束 -->