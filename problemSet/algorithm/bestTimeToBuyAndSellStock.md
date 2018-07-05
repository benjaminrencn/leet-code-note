# <a id="bestTimeToBuyAndSellStock"></a>买卖股票的最佳时机&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.bestTimeToBuyAndSellStock] #

## 描述 ##

给定一个数组，它的第 i 个元素是一支给定股票第 i 天的价格。

如果你最多只允许完成一笔交易（即买入和卖出一支股票），设计一个算法来计算你所能获取的最大利润。

注意你不能在买入股票前卖出股票。

示例 1:

> 输入: [7,1,5,3,6,4]  
> 输出: 5  
> 解释: 在第 2 天（股票价格 = 1）的时候买入，在第 5 天（股票价格 = 6）的时候卖出，最大利润 = 6-1 = 5 。  
> 注意利润不能是 7-1 = 6, 因为卖出价格需要大于买入价格。

示例 2:

> 输入: [7,6,4,3,1]  
> 输出: 0  
> 解释: 在这种情况下, 没有交易完成, 所以最大利润为 0。

## 解答 ##

暴力法

`500ms` `19.07%`

```javascript
/**
 * @param {number[]} prices
 * @return {number}
 */
var maxProfit = function(prices) {
  let profit = 0;
  let pLength = prices.length;
  for (let i = 0; i < pLength - 1; i ++) {
    for (let j = i + 1; j < pLength; j ++) {
      let different = prices[j] - prices[i];
      profit = different > profit ? different : profit;
    }
  }
  return profit;
};
```

最低价格最高收益

`92ms` `48.73%`

```javascript
/**
 * @param {number[]} prices
 * @return {number}
 */
var maxProfit = function(prices) {
  let minPrice = prices[0], maxProfit = 0;
  let pLength = prices.length;
  for (let i = 0; i < pLength; i ++) {
    minPrice = prices[i] < minPrice ? prices[i] : minPrice;
    let profit = prices[i] - minPrice;
    maxProfit = profit > maxProfit ? profit : maxProfit;
  }
  return maxProfit;
};
```

Kadane 算法

`84ms` `74.58%`

```javascript
/**
 * @param {number[]} prices
 * @return {number}
 */
var maxProfit = function(prices) {
  if (!prices || prices.length < 2) {
    return 0;
  }
  let current = 0, max = 0;
  let pLength = prices.length;
  for (let i = 1; i < pLength; i ++) {
    current = Math.max(0, current += prices[i] - prices[i - 1]);
    max = Math.max(current, max);
  }
  return max;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 买卖股票的最佳时机  
  <https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock/description/>
* LeetCode problems best-time-to-buy-and-sell-stock  
  <https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/>
* LeetCode articles best-time-to-buy-and-sell-stock  
  <https://leetcode.com/articles/best-time-to-buy-and-sell-stock/>
* LeetCode problems best-time-to-buy-and-sell-stock Discuss Kadane's Algorithm - Since no one has mentioned about this so far :) (In case if interviewer twists the input) - andyreadsall  
  <https://leetcode.com/problems/best-time-to-buy-and-sell-stock/discuss/39038/Kadane's-Algorithm-Since-no-one-has-mentioned-about-this-so-far-:)-(In-case-if-interviewer-twists-the-input)>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.bestTimeToBuyAndSellStock]: ../../README.md#problemSet.algorithm.bestTimeToBuyAndSellStock "README"
<!-- 链接 结束 -->