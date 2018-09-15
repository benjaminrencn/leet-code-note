# <a id="findTheDifference"></a>找不同&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.findTheDifference] #

## 描述 ##

给定两个字符串 s 和 t，它们只包含小写字母。

字符串 t 由字符串 s 随机重排，然后在随机位置添加一个字母。

请找出在 t 中被添加的字母。
 
示例:

> 输入：  
> s = "abcd"  
> t = "abcde"  
>
> 输出：  
> e
>
> 解释：  
> 'e' 是那个被添加的字母。

## 解答 ##

2个哈希表

`92ms` `58.33%`

```javascript
/**
 * @param {string} s
 * @param {string} t
 * @return {character}
 */
var findTheDifference = function(s, t) {
  let sMap = {}, tMap = {};
  
  for (let i in s) {
    sMap[s[i]] = sMap[s[i]] ? ++ sMap[s[i]] : 1;
  }
  for (let i in t) {
    tMap[t[i]] = tMap[t[i]] ? ++ tMap[t[i]] : 1;
  }

  for (let i in tMap) {
    if (!sMap[i] || sMap[i] < tMap[i]) { return i; }
  }
};
```

ascii码

`100ms` `37.50%`

```javascript
/**
 * @param {string} s
 * @param {string} t
 * @return {character}
 */
var findTheDifference = function(s, t) {
  let sSum = 0, tSum = 0;
  for (let i in s) {
    sSum += s[i].charCodeAt();
  }
  for (let i in t) {
    tSum += t[i].charCodeAt();
  }
  return String.fromCharCode(tSum - sSum);
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 找不同  
  <https://leetcode-cn.com/problems/find-the-difference/description/>
* LeetCode problems find-the-difference  
  <https://leetcode.com/problems/find-the-difference/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.findTheDifference]: ../../README.md#problemSet.algorithm.findTheDifference "README"
<!-- 链接 结束 -->