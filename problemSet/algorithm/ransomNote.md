# <a id="ransomNote"></a>赎金信&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.ransomNote] #

## 描述 ##

给定一个赎金信 (ransom) 字符串和一个杂志(magazine)字符串，判断第一个字符串 ransom 能不能由第二个字符串 magazines 里面的字符构成。如果可以构成，返回 true ；否则返回 false。

(题目说明：为了不暴露赎金信字迹，要从杂志上搜索各个需要的字母，组成单词来表达意思。)

注意：

你可以假设两个字符串均只含有小写字母。

> canConstruct("a", "b") -> false  
> canConstruct("aa", "ab") -> false  
> canConstruct("aa", "aab") -> true

## 解答 ##

Array.indexOf Array.shift Array.splice

`108ms` `74.68%`

```javascript
/**
 * @param {string} ransomNote
 * @param {string} magazine
 * @return {boolean}
 */
var canConstruct = function(ransomNote, magazine) {
  let letter, index;

  if (ransomNote.length > magazine.length) { return false; }

  ransomNote = ransomNote.split('');
  magazine = magazine.split('');

  while (ransomNote.length) {
    letter = ransomNote[0];
    index = magazine.indexOf(letter);
    if (index === -1) { return false; }
    ransomNote.shift();
    magazine.splice(index, 1);
  }

  return true;
};
```

2个哈希表

`256ms` `13.92%`

```javascript
/**
 * @param {string} ransomNote
 * @param {string} magazine
 * @return {boolean}
 */
var canConstruct = function(ransomNote, magazine) {
  let rLetters = {}, mLetters = {};

  for (let i in ransomNote) {
    rLetters[ransomNote[i]] = rLetters[ransomNote[i]] ? ++rLetters[ransomNote[i]] : 1;
  }
  for (let i in magazine) {
    mLetters[magazine[i]] = mLetters[magazine[i]] ? ++mLetters[magazine[i]] : 1;
  }

  for (let i in rLetters) {
    if (!mLetters[i] || rLetters[i] > mLetters[i]) { return false; }
  }

  return true;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 赎金信  
  <https://leetcode-cn.com/problems/ransom-note/description/>
* LeetCode problems ransom-note  
  <https://leetcode.com/problems/ransom-note/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.ransomNote]: ../../README.md#problemSet.algorithm.ransomNote "README"
<!-- 链接 结束 -->