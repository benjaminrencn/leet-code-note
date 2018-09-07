# <a id="addDigits"></a>各位相加&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.addDigits] #

## 描述 ##

示例:

> 输入: 38  
> 输出: 2  
> 解释: 各位相加的过程为：3 + 8 = 11, 1 + 1 = 2。 由于 2 是一位数，所以返回 2。

进阶:

你可以不使用循环或者递归，且在 O(1) 时间复杂度内解决这个问题吗？

## 解答 ##

递归法

`88ms` `92.86%`

```javascript
/**
 * @param {number} num
 * @return {number}
 */
var addDigits = function(num) {
  let sum =  0;
  num = String(num);
  for (let i = 0; i < num.length; i ++) {
    sum += +num[i];
  }
  if (sum < 10) {
    return sum;
  } else {
    return addDigits(sum);
  }
};
```

迭代法

`128ms` `19.64%`

```javascript
/**
 * @param {number} num
 * @return {number}
 */
var addDigits = function(num) {
  let sum =  0;
  num = String(num);
  while (+num >= 10) {
    sum = 0;
    for (let i in num) {
      sum += +num[i];
    }
    num = String(sum);
  }
  return +num;
};

```

数据样例分析

`96ms` `87.50%`

```javascript
/**
 * @param {number} num
 * @return {number}
 */
var addDigits = function(num) {
  return 1 + (num - 1) % 9;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 各位相加  
  <https://leetcode-cn.com/problems/add-digits/description/>
* LeetCode problems add-digits  
  <https://leetcode.com/problems/add-digits/description/>
* LeetCode 258. Add Digits（数位相加） - jmspan
  <https://blog.csdn.net/jmspan/article/details/51103086>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.addDigits]: ../../README.md#problemSet.algorithm.addDigits "README"
<!-- 链接 结束 -->