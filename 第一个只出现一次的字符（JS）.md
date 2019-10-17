# 第一个只出现一次的字符（JS）

## 问题描述

在一个字符串(0<=字符串长度<=10000，全部由字母组成)中找到第一个只出现一次的字符,并返回它的位置, 如果没有则返回 -1（需要区分大小写）.

## 解题思路

```javascript
function FirstNotRepeatingChar(str)
{
    // write code here
    let arr = str.split("");
    let temp1 = "0";
    let temp2 = "0";
    let temp = 0;
    // 先查该元素有没有重复
    for(let i = 0; i < arr.length; i++){
        temp1 = arr.indexOf(arr[i],i+1); // 找出是否有重复值
        temp2 = arr.indexOf(arr[i],0); // 排除是它自己
      //  console.log(temp2+" "+i)
        if(temp2 === i && temp1 === -1){
            return i;
        }
    }
    return -1;
}
console.log(FirstNotRepeatingChar("google"))

```

