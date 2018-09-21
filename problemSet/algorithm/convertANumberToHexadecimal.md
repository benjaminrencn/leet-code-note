# <a id="convertANumberToHexadecimal"></a>数字转换为十六进制数&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.convertANumberToHexadecimal] #

## 描述 ##

给定一个整数，编写一个算法将这个数转换为十六进制数。对于负整数，我们通常使用 补码运算 方法。

注意:

1. 十六进制中所有字母(a-f)都必须是小写。
2. 十六进制字符串中不能包含多余的前导零。如果要转化的数为0，那么以单个字符'0'来表示；对于其他情况，十六进制字符串中的第一个字符将不会是0字符。
3. 给定的数确保在32位有符号整数范围内。
4. 不能使用任何由库提供的将数字直接转换或格式化为十六进制的方法。

示例 1：

> 输入:  
> 26  
>
> 输出:  
> "1a"

示例 2：

> 输入:  
> -1
>
> 输出:  
> "ffffffff"

## 解答 ##

toString(2) 转换为二进制再转换为十六进制

`64ms` `100.00%`

```javascript
  let binary = '';

  if (num >= 0) {
    binary = num.toString(2);
    binary = Array(binary.length % 4 ? 5 - binary.length % 4 : 0).join('0') + binary
  } else {
    binary = getMinusBinary(num);
  }
  console.log(binary)
  
  return binaryToHex(binary);

  // 获得负数二进制
  function getMinusBinary(num) {
    let minusBinary = (Array(33).join('0') + (-(num + 1)).toString(2)).slice(-32).split('');
    console.log(minusBinary.join(''));
    for (let i in minusBinary) {
      minusBinary[i] = minusBinary[i] === '0' ? '1' : '0';
    }
    return minusBinary.join('');
  }
  // 二进制转换十六进制
  function binaryToHex(binary) {
    let hex = '', temp = '';

    while (binary.length) {
      // 二进制
      temp = binary.slice(0, 4);
      binary = binary.slice(4);
      // 二进制转换成十六进制
      temp = Math.pow(2, 0) * +temp[3] + 
        Math.pow(2, 1) * +temp[2] + 
        Math.pow(2, 2) * +temp[1] + 
        Math.pow(2, 3) * +temp[0] + '';
      switch (temp) {
        case '10': temp = 'a'; break;
        case '11': temp = 'b'; break;
        case '12': temp = 'c'; break;
        case '13': temp = 'd'; break;
        case '14': temp = 'e'; break;
        case '15': temp = 'f'; break;
      }
      hex += temp;
    }

    return hex;
  }
```

## 参考 ##

* LeetCode (中国) 题库 算法 数字转换为十六进制数  
  <https://leetcode-cn.com/problems/convert-a-number-to-hexadecimal/description/>
* LeetCode problems convert-a-number-to-hexadecimal  
  <https://leetcode.com/problems/convert-a-number-to-hexadecimal/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.convertANumberToHexadecimal]: ../../README.md#problemSet.algorithm.convertANumberToHexadecimal "README"
<!-- 链接 结束 -->