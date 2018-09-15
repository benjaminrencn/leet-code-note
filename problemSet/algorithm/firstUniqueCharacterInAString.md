# <a id="firstUniqueCharacterInAString"></a>字符串中的第一个唯一字符&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.firstUniqueCharacterInAString] #

## 描述 ##

给定一个字符串，找到它的第一个不重复的字符，并返回它的索引。如果不存在，则返回 -1。

案例:

> s = "leetcode"  
> 返回 0.
>
> s = "loveleetcode",  
> 返回 2.

## 解答 ##

Array.indexOf Array.lastIndexOf

`276ms` `19.95%`

```javascript
/**
 * @param {string} s
 * @return {number}
 */
var firstUniqChar = function(s) {
  s = s.split('');
  for (let i = 0; i < s.length; i ++) {
    if (s.indexOf(s[i]) === s.lastIndexOf(s[i])) {
      return i;
    }
  }
  return -1;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 字符串中的第一个唯一字符  
  <https://leetcode-cn.com/problems/first-unique-character-in-a-string/description/>
* LeetCode problems first-unique-character-in-a-string  
  <https://leetcode.com/problems/first-unique-character-in-a-string/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.firstUniqueCharacterInAString]: ../../README.md#problemSet.algorithm.firstUniqueCharacterInAString "README"
<!-- 链接 结束 -->