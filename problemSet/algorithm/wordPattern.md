# <a id="wordPattern"></a>单词模式&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.wordPattern] #

## 描述 ##

给定一种 pattern(模式) 和一个字符串 str ，判断 str 是否遵循相同的模式。

这里的遵循指完全匹配，例如， pattern 里的每个字母和字符串 str 中的每个非空单词之间存在着双向连接的对应模式。

示例1:

> 输入: pattern = "abba", str = "dog cat cat dog"  
> 输出: true

示例 2:

> 输入:pattern = "abba", str = "dog cat cat fish"  
> 输出: false

示例 3:

> 输入: pattern = "aaaa", str = "dog cat cat dog"  
> 输出: false

示例 4:

> 输入: pattern = "abba", str = "dog dog dog dog"  
> 输出: false

说明:

你可以假设 pattern 只包含小写字母， str 包含了由单个空格分隔的小写字母。

## 解答 ##

哈希表 分别存 模式 字符串

`72ms` `77.61%`

```javascript
/**
 * @param {string} pattern
 * @param {string} str
 * @return {boolean}
 */
var wordPattern = function(pattern, str) {
  let map = {};
  let patterns = pattern.split('');
  let strs = str.split(' ');

  if (patterns.length !== strs.length) { return false; }
  if (patterns.length === 0) { return true; }
  for (let i = 0; i < patterns.length; i ++) {
    if (map[patterns[i]]) {
      if (map[patterns[i]] !== strs[i]) { return false; }
    } else {
      if (map['s' + strs[i]]) { return false; }
      map[patterns[i]] = strs[i];
      map['s' + strs[i]] = patterns[i];
    }
  }

  return true;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 单词模式  
  <https://leetcode-cn.com/problems/word-pattern/description/>
* LeetCode problems word-pattern  
  <https://leetcode.com/problems/word-pattern/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.wordPattern]: ../../README.md#problemSet.algorithm.wordPattern "README"
<!-- 链接 结束 -->