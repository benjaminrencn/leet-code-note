# <a id="reverseVowelsOfAString"></a>反转字符串中的元音字母&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.reverseVowelsOfAString] #

## 描述 ##

编写一个函数，以字符串作为输入，反转该字符串中的元音字母。

示例 1:

> 输入: "hello"  
> 输出: "holle"

示例 2:

> 输入: "leetcode"  
> 输出: "leotcede"

说明:

元音字母不包含字母"y"。

## 解答 ##

遍历所有原因字母索引在反转

`136ms` `50.57%`

```javascript
/**
 * @param {string} s
 * @return {string}
 */
var reverseVowels = function(s) {
  let vowels = ['a', 'A', 'e', 'E', 'i', 'I', 'o', 'O', 'u', 'U'];
  let vowelArray = [];
  let temp;

  for (let i = 0; i < s.length; i ++) {
    if (vowels.indexOf(s[i]) > -1) { vowelArray.push(i); }
  }
  s = s.split('');
  for (let i = 0; i < vowelArray.length / 2; i ++ ) {
    temp = s[vowelArray[i]];
    s[vowelArray[i]] = s[vowelArray[vowelArray.length - 1 - i]];
    s[vowelArray[vowelArray.length - 1 - i]] = temp;
  }

  return s.join('');
};
```

双指针

`140ms` `45.98%`

```javascript
/**
 * @param {string} s
 * @return {string}
 */
var reverseVowels = function(s) {
  let start = 0, end = s.length - 1, temp;
  s = s.split('');

  while (start < end) {
    if (isVowel(s[start])) {
      while (start < end) {
        if (isVowel(s[end])) {
          temp = s[start];
          s[start] = s[end];
          s[end] = temp;
          end --;
          break;
        }
        end --;
      }
    }
    start ++;
  }

  return s.join('');

  function isVowel(letter) {
    return ['a', 'A', 'e', 'E', 'i', 'I', 'o', 'O', 'u', 'U'].indexOf(letter) > -1;
  }
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 反转字符串中的元音字母  
  <https://leetcode-cn.com/problems/reverse-vowels-of-a-string/description/>
* LeetCode problems reverse-vowels-of-a-string  
  <https://leetcode.com/problems/reverse-vowels-of-a-string/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.reverseVowelsOfAString]: ../../README.md#problemSet.algorithm.reverseVowelsOfAString "README"
<!-- 链接 结束 -->