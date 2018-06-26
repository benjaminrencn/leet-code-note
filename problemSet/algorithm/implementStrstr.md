# <a id="implementStrstr"></a>实现 strStr()&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.implementStrstr] #

## 描述 ##

实现 strStr() 函数。

给定一个 haystack 字符串和一个 needle 字符串，在 haystack 字符串中找出 needle 字符串出现的第一个位置 (从0开始)。如果不存在，则返回  -1。

示例 1:

> 输入: haystack = "hello", needle = "ll"
> 输出: 2

示例 2:

> 输入: haystack = "aaaaa", needle = "bba"
> 输出: -1

说明:

当 needle 是空字符串时，我们应当返回什么值呢？这是一个在面试中很好的问题。

对于本题而言，当 needle 是空字符串时我们应当返回 0 。这与C语言的 strstr() 以及 Java的 indexOf() 定义相符。

## 解答 ##

子字符串

72ms

```javascript
/**
 * @param {string} haystack
 * @param {string} needle
 * @return {number}
 */
var strStr = function(haystack, needle) {
  if (!needle || needle.length === 0) {
    return 0;
  }
  let i;
  for (i = 0; i < haystack.length; i ++) {
    if (haystack.slice(i, i + needle.length) === needle) {
      return i;
    }
  }
  return -1;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 实现 strStr()  
  <https://leetcode-cn.com/problems/implement-strstr/description/>
* LeetCode problems implement-strstr  
  <https://leetcode.com/problems/implement-strstr/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.implementStrstr]: ../../README.md#problemSet.algorithm.implementStrstr "README"
<!-- 链接 结束 -->