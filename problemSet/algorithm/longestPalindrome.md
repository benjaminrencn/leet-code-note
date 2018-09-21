# <a id="longestPalindrome"></a>最长回文串&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.longestPalindrome] #

## 描述 ##

给定一个包含大写字母和小写字母的字符串，找到通过这些字母构造成的最长的回文串。

在构造过程中，请注意区分大小写。比如 "Aa" 不能当做一个回文字符串。

注意:
假设字符串的长度不会超过 1010。

示例 1:

> 输入:  
> "abccccdd"
>
> 输出:  
> 7

解释:
我们可以构造的最长的回文串是"dccaccd", 它的长度是 7。

## 解答 ##

哈希表法 delete

`92ms` `50.85%`

```javascript
/**
 * @param {string} s
 * @return {number}
 */
var longestPalindrome = function(s) {
  let map = {}, length = 0;

  for (let i in s) {
    if (map[s[i]]) {
      length += 2;
      delete map[s[i]];
    } else {
      map[s[i]] = true;
    }
  }
  if (Object.keys(map).length > 0) { length ++; }
  
  return length;
};
```

哈希表计数法

`84ms` `79.66%`

```javascript
/**
 * @param {string} s
 * @return {number}
 */
var longestPalindrome = function(s) {
  let map = {}, singleFlag = false, length = 0;

  for (let i in s) {
    map[s[i]] = map[s[i]] ? map[s[i]] + 1 : 1;
  }
  for (let i in map) {
    length += map[i] - map[i] % 2;
    if (map[i] % 2) { singleFlag = true; } 
  }
  if (singleFlag) { length ++; }
  
  return length;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 最长回文串  
  <https://leetcode-cn.com/problems/longest-palindrome/description/>
* LeetCode problems longest-palindrome  
  <https://leetcode.com/problems/longest-palindrome/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.longestPalindrome]: ../../README.md#problemSet.algorithm.longestPalindrome "README"
<!-- 链接 结束 -->