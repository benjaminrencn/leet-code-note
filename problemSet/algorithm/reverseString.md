# <a id="reverseString"></a>反转字符串&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.reverseString] #

## 描述 ##

编写一个函数，其作用是将输入的字符串反转过来。

示例 1:

> 输入: "hello"  
> 输出: "olleh"

示例 2:

> 输入: "A man, a plan, a canal: Panama"  
> 输出: "amanaP :lanac a ,nalp a ,nam A"

## 解答 ##

String.split Array.reserve Array.join

`104ms` `73.67%`

```javascript
/**
 * @param {string} s
 * @return {string}
 */
var reverseString = function(s) {
  let tempArray = s.split('');
  tempArray.reverse();
  return tempArray.join('');
};
```

遍历法

`132ms` `25.42%`

```javascript
/**
 * @param {string} s
 * @return {string}
 */
var reverseString = function(s) {
  let temp = '';
  for (let i = s.length - 1; i >= 0; i --) {
    temp += s[i];
  }
  return temp;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 反转字符串  
  <https://leetcode-cn.com/problems/reverse-string/description/>
* LeetCode problems reverse-string  
  <https://leetcode.com/problems/reverse-string/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.reverseString]: ../../README.md#problemSet.algorithm.reverseString "README"
<!-- 链接 结束 -->