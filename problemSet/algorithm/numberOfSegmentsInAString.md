# <a id="numberOfSegmentsInAString"></a>字符串中的单词数&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.numberOfSegmentsInAString] #

## 描述 ##

统计字符串中的单词个数，这里的单词指的是连续的不是空格的字符。

请注意，你可以假定字符串里不包括任何不可打印的字符。

示例:

> 输入: "Hello, my name is John"  
> 输出: 5

## 解答 ##

String.trim() String.match()

`72ms` `61.54%`

```javascript
/**
 * @param {string} s
 * @return {number}
 */
var countSegments = function(s) {
  let match = s.trim().match(/\s+/g);
  if (!s.trim()) { return 0; }
  return match && match.length + 1 || 1;
};
```

String.trim() String.split()

`76ms` `48.35%`

```javascript
/**
 * @param {string} s
 * @return {number}
 */
var countSegments = function(s) {
  let trimString = s.trim();
  if (!trimString) { return 0; }
  return trimString.split(/\s+/).length;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 字符串中的单词数  
  <https://leetcode-cn.com/problems/number-of-segments-in-a-string/description/>
* LeetCode problems number-of-segments-in-a-string  
  <https://leetcode.com/problems/number-of-segments-in-a-string/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.numberOfSegmentsInAString]: ../../README.md#problemSet.algorithm.numberOfSegmentsInAString "README"
<!-- 链接 结束 -->