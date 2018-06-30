# <a id="countAndSay"></a>报数&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.countAndSay] #

## 描述 ##

报数序列是指一个整数序列，按照其中的整数的顺序进行报数，得到下一个数。其前五项如下：

> 1. 1
> 1. 11
> 1. 21
> 1. 1211
> 1. 111221

`1` 被读作  `"one 1"`  (`"一个一"`) , 即 `11`。  
`11` 被读作 `"two 1s"` (`"两个一"`）, 即 `21`。  
`21` 被读作 `"one 2"`,  `"one 1"` （`"一个二"` , `"一个一"`) , 即 `1211`。

给定一个正整数 n ，输出报数序列的第 n 项。

注意：整数顺序将表示为一个字符串。

示例 1:

> 输入: 1  
> 输出: "1"

示例 2:

> 输入: 4  
> 输出: "1211"

## 解答 ##

报数

`68ms` `96.48%`

```javascript
/**
 * @param {number} n
 * @return {string}
 */
var countAndSay = function(n) {
  let number = '1';
  let temp = number[0];
  let count = 0;
  let result = '';

  for (let i = 0; i < n - 1; i ++) {
    for (let j = 0; j < number.length; j ++) {
      if (number[j] === temp) {
        count ++;
      } else {
        result += count + temp;
        temp = number[j];
        count  = 1;
      }
      if (j === number.length - 1) {
        result += count + temp;
      }
    }
    number = result;
    temp = number[0];
    count = 0;
    result = '';
  }

  return number;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 报数  
  <https://leetcode-cn.com/problems/count-and-say/description/>
* LeetCode problems count-and-say  
  <https://leetcode.com/problems/count-and-say/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.countAndSay]: ../../README.md#problemSet.algorithm.countAndSay "README"
<!-- 链接 结束 -->