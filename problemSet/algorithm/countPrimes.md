# <a id="countPrimes"></a>计数质数&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.countPrimes] #

## 描述 ##

统计所有小于非负整数 n 的质数的数量。

示例:

> 输入: 10
> 输出: 4
> 解释: 小于 10 的质数一共有 4 个, 它们是 2, 3, 5, 7 。

## 解答 ##

暴力法 用小于次方跟的素数求余判断素数 遍历奇数

`344ms` `58.46%`

```javascript
/**
 * @param {number} n
 * @return {number}
 */
var countPrimes = function(n) {
  let primes = [];
  let prime = 2;
  let sqrt = 0;
  let i = 0;

  if (n <= 2) {
    return 0;
  } else {
    primes.push(2);
  }

  for (prime = 3; prime < n; prime += 2) {
    sqrt = Math.sqrt(prime);
    for (i = 0; i < primes.length && primes[i] < sqrt; i ++) {
      if (prime % (primes[i] || 2) === 0) {
        break;
      }
    }
    if (primes[i] > sqrt && prime !== 2) { primes.push(prime); }
  }
  return primes.length;
};
```

计算合数法

超出内存限制

```javascript
/**
 * @param {number} n
 * @return {number}
 */
var countPrimes = function(n) {
  if (n < 3) { return 0; }
  let composites = {};
  let i = 2, j = 2, count = 0;
  for (i = 2; i < n; i ++) {
    if (!composites[i]) {
      count ++;
      for (j = 2; i * j < n; j ++) {
        composites[i * j] = true;
      }
    }
  }
  return count;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 计数质数  
  <https://leetcode-cn.com/problems/count-primes/description/>
* LeetCode problems count-primes  
  <https://leetcode.com/problems/count-primes/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.countPrimes]: ../../README.md#problemSet.algorithm.countPrimes "README"
<!-- 链接 结束 -->