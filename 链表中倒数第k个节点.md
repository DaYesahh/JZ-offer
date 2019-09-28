# 链表中倒数第k个节点

输入一个链表，输出该链表中倒数第k个结点。

- 解决思路：先正着遍历一波，获取链表的长度。再遍历到n-k的位置上，即可。

  ```java
  /*
  public class ListNode {
      int val;
      ListNode next = null;
  
      ListNode(int val) {
          this.val = val;
      }
  }*/
  public class Solution {
      public ListNode FindKthToTail(ListNode head,int k) {
          ListNode p = head;
          ListNode p2 = head;
          int n = 1;
          int n2 = 1;
          if(head == null){
              return null;
          }
         while(p.next != null){
             p = p.next;
             n++;
         }
       if(k >n || k <= 0){
           return null;
       }
         while(n2 <= n-k){
             p2 = p2.next;
             n2++;
         }  
          return p2;
      }
  }
  ```


