leetCode: 2.Add Two Numbers
=============================

Problem:
-------------
You are given two linked lists representing two non-negative numbers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

Example:
-------------
Input: (2 -> 4 -> 3) + (5 -> 6 -> 4)
Output: 7 -> 0 -> 8

Solution:
-------------

::

  /** 
   * Definition for singly-linked list. 
   * function ListNode(val) { 
   *     this.val = val; 
   *     this.next = null; 
   * } 
   */  
  /** 
   * @param {ListNode} l1 
   * @param {ListNode} l2 
   * @return {ListNode} 
   */  
  var addTwoNumbers = function(l1, l2) {  
      var carry = 0,  
          head = new ListNode(0),  
          p = head;  
        
      while(l1 !== null || l2 !== null || carry === 1) {  
          val1 = l1 === null ? 0 : l1.val;  
          val2 = l2 === null ? 0 : l2.val;  
            
          p.next = new ListNode((val1 + val2 + carry) % 10);  
          carry = (val1 + val2 + carry) >= 10 ? 1 : 0;  
            
          l1 = l1 === null ? null : l1.next;  
          l2 = l2 === null ? null : l2.next;  
          p = p.next;  
      }  
        
      return head.next;  
  };


