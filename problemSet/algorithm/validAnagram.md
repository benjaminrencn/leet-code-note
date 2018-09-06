# <a id="validAnagram"></a>有效的字母异位词&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.validAnagram] #

## 描述 ##

给定两个字符串 s 和 t ，编写一个函数来判断 t 是否是 s 的一个字母异位词。

示例 1:

> 输入: s = "anagram", t = "nagaram"  
> 输出: true

示例 2:

> 输入: s = "rat", t = "car"  
> 输出: false

说明:

你可以假设字符串只包含小写字母。

进阶:

如果输入字符串包含 unicode 字符怎么办？你能否调整你的解法来应对这种情况？

## 解答 ##

indexOf replace

`592ms` `12.37%`

```javascript
/**
 * @param {string} s
 * @param {string} t
 * @return {boolean}
 */
var isAnagram = function(s, t) {
  if (s.length !== t.length) {
    return false;
  }
  while (s.length) {
    if (t.indexOf(s[0]) > -1) {
      t = t.replace(s[0], '');
      s = s.replace(s[0], '');
    } else {
      return false;
    }
  }
  return true;
};
```

2个哈希图

`156ms` `50.00%`

```javascript
/**
 * @param {string} s
 * @param {string} t
 * @return {boolean}
 */
var isAnagram = function(s, t) {
  if (s.length !== t.length) {
    return false;
  }
  let sKeys = getKeys(s);
  let tKeys = getKeys(t);
  for (let i in sKeys) {
    if (sKeys[i] !== tKeys[i]) {
      return  false;
    }
  }
  return true;

  function getKeys(string) {
    let keys = {};
    for (let i in string) {
      keys[string[i]] = keys[string[i]] ? ++ keys[string[i]] : 1;
    }
    return keys;
  }
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 有效的字母异位词  
  <https://leetcode-cn.com/problems/valid-anagram/description/>
* LeetCode problems valid-anagram  
  <https://leetcode.com/problems/valid-anagram/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.validAnagram]: ../../README.md#problemSet.algorithm.validAnagram "README"
<!-- 链接 结束 -->