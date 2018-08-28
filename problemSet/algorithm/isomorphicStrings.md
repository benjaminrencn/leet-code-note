# <a id="isomorphicStrings"></a>同构字符串&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.isomorphicStrings] #

## 描述 ##

给定两个字符串 s 和 t，判断它们是否是同构的。

如果 s 中的字符可以被替换得到 t ，那么这两个字符串是同构的。

所有出现的字符都必须用另一个字符替换，同时保留字符的顺序。两个字符不能映射到同一个字符上，但字符可以映射自己本身。

示例 1:

> 输入: s = "egg", t = "add"  
> 输出: true

示例 2:

> 输入: s = "foo", t = "bar"  
> 输出: false

示例 3:

> 输入: s = "paper", t = "title"  
> 输出: true

说明:
你可以假设 s 和 t 具有相同的长度。

## 解答 ##

2个哈希表存对方数组字符

`108ms` `45.45%`

```javascript
/**
 * @param {string} s
 * @param {string} t
 * @return {boolean}
 */
var isIsomorphic = function(s, t) {
  let i = 0;
  let s2t = {};
  let t2s = {};

  for (i = 0; i < s.length; i ++) {
    if (!s2t[s[i]] && !t2s[t[i]]) {
      s2t[s[i]] = t[i];
      t2s[t[i]] = s[i];
    } else if (s2t[s[i]] !== t[i] || t2s[t[i]] !== s[i]) {
      return false;
    }
  }
  return true;
};
```

2个哈希表存索引

`84ms` `84.55%`

```javascript
/**
 * @param {string} s
 * @param {string} t
 * @return {boolean}
 */
var isIsomorphic = function(s, t) {
  let i = 0;
  let sMap = {};
  let tMap = {};

  for (i = 0; i < s.length; i ++) {
    if (sMap[s[i]] !== tMap[t[i]]) {
      return false;
    } else {
      sMap[s[i]] = i;
      tMap[t[i]] = i;
    }
  }
  return true;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 同构字符串  
  <https://leetcode-cn.com/problems/isomorphic-strings/description/>
* LeetCode problems isomorphic-strings  
  <https://leetcode.com/problems/isomorphic-strings/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.isomorphicStrings]: ../../README.md#problemSet.algorithm.isomorphicStrings "README"
<!-- 链接 结束 -->