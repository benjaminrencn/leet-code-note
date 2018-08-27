# <a id="happyNumber"></a>快乐数&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.happyNumber] #

## 描述 ##

编写一个算法来判断一个数是不是“快乐数”。

一个“快乐数”定义为：对于一个正整数，每一次将该数替换为它每个位置上的数字的平方和，然后重复这个过程直到这个数变为 1，也可能是无限循环但始终变不到 1。如果可以变为 1，那么这个数就是快乐数。

示例:

> 输入: 19  
> 输出: true  
> 解释:  
> 1<sup>2</sup> + 9<sup>2</sup> = 82  
> 8<sup>2</sup> + 2<sup>2</sup> = 68  
> 6<sup>2</sup> + 8<sup>2</sup> = 100  
> 1<sup>2</sup> + 0<sup>2</sup> + 0<sup>2</sup> = 1

## 解答 ##

暴力法

`72ms` `94.35%`

```javascript
/**
 * @param {number} n
 * @return {boolean}
 */
var isHappy = function(n) {
  if (!n) { return 0; }
  let sums = [];
  let sum = 0;
  let nums = [];
  while (n !== 1) {
    sum = 0;
    nums = String(n).split('');
    for (let i = 0; i < nums.length; i ++) {
      sum += Math.pow(+nums[i], 2);
    }
    if (sums.indexOf(sum) > -1) {
      return false;
    }
    sums.push(sum);
    n = sum;
  }
  return true;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 快乐数  
  <https://leetcode-cn.com/problems/happy-number/description/>
* LeetCode problems happy-number  
  <https://leetcode.com/problems/happy-number/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.happyNumber]: ../../README.md#problemSet.algorithm.happyNumber "README"
<!-- 链接 结束 -->