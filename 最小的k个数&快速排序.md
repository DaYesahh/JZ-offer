# 快速排序

编程思想：

- 随机找基准值，编程方便可以一直找第一个。左指针left，右指针right，基准值位置index

- 从右往左遍历，找到第一个比基准值小的值b，b则放到左指针的位置上，左指针右移，index等于右指针的位置。

- 从左到右遍历，找到第一个比基准值大的值a，a放到右指针位置上，右指针左移。index等于左指针位置。

- 一轮结束后，index处的位置填上基准值。

- 平均复杂度为nlogn，最坏情况的复杂度是n^2，来自冒泡排序，最坏则是冒泡排序。

- 题目：最小的k个数

- 编码：

- ```java
  import java.util.ArrayList;
  
  public class Solution {
  
      public ArrayList<Integer> GetLeastNumbers_Solution(int [] input, int k) {
          ArrayList<Integer> arrlist = new ArrayList<Integer>();
          if (k > input.length){
              return arrlist;
          }
          int [] arr = new int[input.length];
          for (int i = 0; i < input.length; i++){
              arr[i] = input[i];
          }
          // 采用快速排序
          // 找到基准值，从右往左是比基准元素小的，从左往右为比基准元素大的。
          // 基准值
          Kuai(arr,0,arr.length - 1);
          for (int i = 0; i < k; i++){
              arrlist.add(i,arr[i]);
          }
          return arrlist;
      }
      public void Kuai(int [] arr, int startindex, int endindex){
          if (startindex >= endindex){
              return;
          }
          int po = arr[startindex];
          // 获取中间基准值位置
          int poindex = getIndex(arr,startindex,endindex);
          Kuai(arr,startindex,poindex-1);// 基准值已定好位置，不需要再动
          Kuai(arr,poindex + 1, endindex);// 基准值已定好位置，不需要再动
      }
      public int getIndex(int [] arr, int startindex, int endindex){
          // 找基准元素和基准元素的位置
          int povit = arr[startindex];
          int index = startindex;
          int right = endindex;
          int left = startindex;
          while(right>=left){
              while(left <= right){
                  // 从右往左找比基准元素小的
                  if (arr[right] <= povit){
                      arr[left] = arr[right];
                      index = right;
                      left++;
                      break;
                  }
                  right--;
              }
              // 从左往右，找比基准元素大的
              while(left <= right){
                  if (arr[left] > povit){
                      arr[right] = arr[left];
                      index = left;
                      right--;
                      break;
                  }
                  left++;
              }
          }
          arr[index] = povit;
          return index;
      }
  }
  ```

- 
