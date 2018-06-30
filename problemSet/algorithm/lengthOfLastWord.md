# <a id="lengthOfLastWord"></a>最后一个单词的长度&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.lengthOfLastWord] #

## 描述 ##

给定一个仅包含大小写字母和空格 `' '` 的字符串，返回其最后一个单词的长度。

如果不存在最后一个单词，请返回 0 。

说明：一个单词是指由字母组成，但不包含任何空格的字符串。

示例:

> 输入: "Hello World"  
> 输出: 5

## 解答 ##

trim() split() pop() length

`72ms` `67.07%`

```javascript
/**
 * @param {string} s
 * @return {number}
 */
var lengthOfLastWord = function(s) {
  s = s.trim();
  if (!s) {
    return 0;
  }

  return s.split(' ').pop().length;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 最后一个单词的长度  
  <https://leetcode-cn.com/problems/length-of-last-word/description/>
* LeetCode problems length-of-last-word  
  <https://leetcode.com/problems/length-of-last-word/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.lengthOfLastWord]: ../../README.md#problemSet.algorithm.lengthOfLastWord "README"
<!-- 链接 结束 -->