# <a id="validPalindrome"></a>验证回文串&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.validPalindrome] #

## 描述 ##

给定一个字符串，验证它是否是回文串，只考虑字母和数字字符，可以忽略字母的大小写。

说明：本题中，我们将空字符串定义为有效的回文串。

示例 1:

> 输入: "A man, a plan, a canal: Panama"  
> 输出: true

示例 2:

> 输入: "race a car"  
> 输出: false

## 解答 ##

replace加头尾比较

`88 ms` `95.15%`

```javascript
/**
 * @param {string} s
 * @return {boolean}
 */
var isPalindrome = function(s) {
  s = s.toLowerCase().replace(/[^A-Za-z\d]/g, '');
  let length = s.length;
  for (let i = 0; i < length / 2 ; i ++) {
    if (s[i] !== s[length - 1 - i]) {
      return false;
    }
  }
  return true;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 验证回文串  
  <https://leetcode-cn.com/problems/valid-palindrome/description/>
* LeetCode problems valid-palindrome  
  <https://leetcode.com/problems/valid-palindrome/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.validPalindrome]: ../../README.md#problemSet.algorithm.validPalindrome "README"
<!-- 链接 结束 -->