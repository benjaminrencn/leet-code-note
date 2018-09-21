# <a id="binaryWatch"></a>二进制手表&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.binaryWatch] #

## 描述 ##

二进制手表顶部有 4 个 LED 代表小时（0-11），底部的 6 个 LED 代表分钟（0-59）。

每个 LED 代表一个 0 或 1，最低位在右侧。

例如，上面的二进制手表读取 “3:25”。

给定一个非负整数 n 代表当前 LED 亮着的数量，返回所有可能的时间。

案例:

> 输入: n = 1  
> 返回: ["1:00", "2:00", "4:00", "8:00", "0:01", "0:02", "0:04", "0:08", "0:16", "0:32"]

注意事项:

* 输出的顺序没有要求。
* 小时不会以零开头，比如 “01:00” 是不允许的，应为 “1:00”。
* 分钟必须由两位数组成，可能会以零开头，比如 “10:2” 是无效的，应为 “10:02”。

## 解答 ##

遍历 0~11 0~59

`76ms` `76.00%`

```javascript
/**
 * @param {number} num
 * @return {string[]}
 */
var readBinaryWatch = function(num) {
  let times = [], time = '', hour = 0, h = 0, minute = 0, m = 0;

  for (hour = 0; hour <= 11; hour ++) {
    h = binaryNumber(hour);
    if (h <= num && h <= 3) {
      for (minute = 0; minute <= 59; minute ++) {
        m = binaryNumber(minute);
        if (h + m === num && m <= 5) {
          time = '' + hour + ':' + (minute < 10 ? '0' + minute : minute);
          times.push(time);
        }
      }
    }
  }

  return times;

  // number 二进制 1 的个数
  function binaryNumber(number) {
    let binaries = number.toString(2).split('');
    let count = 0;
    for (let i in binaries) {
      count += +binaries[i];
    }
    return count;
  }
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 二进制手表  
  <https://leetcode-cn.com/problems/binary-watch/description/>
* LeetCode problems binary-watch  
  <https://leetcode.com/problems/binary-watch/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.binaryWatch]: ../../README.md#problemSet.algorithm.binaryWatch "README"
<!-- 链接 结束 -->