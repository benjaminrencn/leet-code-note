# <a id="fizzBuzz"></a>Fizz Buzz&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.fizzBuzz] #

## 描述 ##

写一个程序，输出从 1 到 n 数字的字符串表示。

1. 如果 n 是3的倍数，输出“Fizz”；

2. 如果 n 是5的倍数，输出“Buzz”；

3. 如果 n 同时是3和5的倍数，输出 “FizzBuzz”。

示例：

> n = 15,
>
> 返回:
> ```
> [
>   "1",
>   "2",
>   "Fizz",
>   "4",
>   "Buzz",
>   "Fizz",
>   "7",
>   "8",
>   "Fizz",
>   "Buzz",
>   "11",
>   "Fizz",
>   "13",
>   "14",
>   "FizzBuzz"
> ]
> ```

## 解答 ##

遍历法

`128ms` `13.99%`

```javascript
/**
 * @param {number} n
 * @return {string[]}
 */
var fizzBuzz = function(n) {
  let results = [], result = '';
  for (let i = 1; i <= n; i ++) {
    if (!(i % 3) && !(i % 5)) {
      result = 'FizzBuzz'
    } else if (!(i % 3)) {
      result = 'Fizz'
    } else if (!(i % 5)) {
      result = 'Buzz'
    } else {
      result = i.toString();
    }
    results.push(result);
  }
  return results;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 Fizz Buzz  
  <https://leetcode-cn.com/problems/fizz-buzz/description/>
* LeetCode problems fizz-buzz  
  <https://leetcode.com/problems/fizz-buzz/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.fizzBuzz]: ../../README.md#problemSet.algorithm.fizzBuzz "README"
<!-- 链接 结束 -->