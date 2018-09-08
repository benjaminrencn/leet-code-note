# <a id="firstBadVersion"></a>第一个错误的版本&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.firstBadVersion] #

## 描述 ##

你是产品经理，目前正在带领一个团队开发新的产品。不幸的是，你的产品的最新版本没有通过质量检测。由于每个版本都是基于之前的版本开发的，所以错误的版本之后的所有版本都是错的。

假设你有 n 个版本 [1, 2, ..., n]，你想找出导致之后所有版本出错的第一个错误的版本。

你可以通过调用 bool isBadVersion(version) 接口来判断版本号 version 是否在单元测试中出错。实现一个函数来查找第一个错误的版本。你应该尽量减少对调用 API 的次数。

示例:

> 给定 n = 5，并且 version = 4 是第一个错误的版本。
>
> 调用 isBadVersion(3) -> false  
> 调用 isBadVersion(5) -> true  
> 调用 isBadVersion(4) -> true
>
> 所以，4 是第一个错误的版本。

## 解答 ##

二分法

`92ms` `21.09%`

```javascript
/**
 * Definition for isBadVersion()
 * 
 * @param {integer} version number
 * @return {boolean} whether the version is bad
 * isBadVersion = function(version) {
 *     ...
 * };
 */

/**
 * @param {function} isBadVersion()
 * @return {function}
 */
var solution = function(isBadVersion) {
  /**
   * @param {integer} n Total versions
   * @return {integer} The first bad version
   */
  return function(n) {
    if (isBadVersion(1)) { return 1; }

    let good = 1, bad = n, temp = 0;

    while (!(!isBadVersion(good) && isBadVersion(bad) && good + 1 === bad)) {
      temp = Math.floor((good + bad) / 2);
      if (isBadVersion(temp)) {
        bad = temp;
      } else {
        good = temp;
      }
    }
    return bad;
  };
};
```

二分法

`72ms` `66.72%`

```javascript
/**
 * Definition for isBadVersion()
 * 
 * @param {integer} version number
 * @return {boolean} whether the version is bad
 * isBadVersion = function(version) {
 *     ...
 * };
 */

/**
 * @param {function} isBadVersion()
 * @return {function}
 */
var solution = function(isBadVersion) {
  /**
   * @param {integer} n Total versions
   * @return {integer} The first bad version
   */
  return function(n) {
    let left = 1, middle = 1, right = n;
    while (left <= right) {
      middle = Math.floor((left + right) / 2);
      if (isBadVersion(middle) == true) {
        right = middle - 1;
      } else {
        left = middle + 1;
      }
    }
    return left;
  };
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 第一个错误的版本  
  <https://leetcode-cn.com/problems/first-bad-version/description/>
* LeetCode problems first-bad-version  
  <https://leetcode.com/problems/first-bad-version/description/>
* LeetCode problems first-bad-version 范例  
  <https://leetcode-cn.com/submissions/detail/6747571/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.firstBadVersion]: ../../README.md#problemSet.algorithm.firstBadVersion "README"
<!-- 链接 结束 -->