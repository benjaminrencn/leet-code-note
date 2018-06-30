# <a id="longestCommonPrefix"></a>最长公共前缀&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.longestCommonPrefix] #

## 描述 ##

编写一个函数来查找字符串数组中的最长公共前缀。

如果不存在公共前缀，返回空字符串 ""。

示例 1:

> 输入: ["flower","flow","flight"]  
> 输出: "fl"

示例 2:

> 输入: ["dog","racecar","car"]  
> 输出: ""  
> 解释: 输入不存在公共前缀。

说明:

所有输入只包含小写字母 a-z 。

## 解答 ##

最短字符串遍历

`80ms` `70.24%`

```javascript
/**
 * @param {string[]} strs
 * @return {string}
 */
var longestCommonPrefix = function(strs) {
  if (!strs || strs.length === 0) {
    return '';
  }
  var prefix = strs[0];
  for (var key in strs) {
    if (prefix.length > strs[key].length) {
      prefix = strs[key];
    }
  }
  console.log(prefix);
  var end = prefix.length;
  for (var i = prefix.length - 1; i >= 0; i --) {
    prefix = prefix.slice(0, i + 1);
    for (var j = 0; j < strs.length; j ++) {
      if (strs[j].indexOf(prefix) !== 0) {
        break;
      } else if (j === strs.length - 1) {
        return prefix;
      }
    }
  }
  return '';
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 最长公共前缀  
  <https://leetcode-cn.com/problems/longest-common-prefix/description/>
* LeetCode problems longest-common-prefix  
  <https://leetcode.com/problems/longest-common-prefix/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.longestCommonPrefix]: ../../README.md#problemSet.algorithm.longestCommonPrefix "README"
<!-- 链接 结束 -->