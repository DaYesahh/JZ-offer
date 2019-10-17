# 数字在排序数组中出现的次数（JS）

## 问题描述

统计一个数字在排序数组中出现的次数。

## 解题思路

```javascript
function GetNumberOfK(data, k)
{
    // write code here
    let count = 0;
    for(let i = 0; i < data.length; i++){
        if (data[i] === k){
            count++;
        }
    }
    return count;
}
var arr = [1,2,3,3,3,3,4,5];
console.log(GetNumberOfK(arr,3))

```

