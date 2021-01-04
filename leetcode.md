# Fibonacci
The Fibonacci numbers, commonly denoted F(n) form a sequence, called the Fibonacci sequence, such that each number is the sum of the two preceding ones, starting from 0 and 1. That is,

F(0) = 0, F(1) = 1
F(n) = F(n - 1) + F(n - 2), for n > 1.
Given n, calculate F(n).

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/fibonacci-number
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。

## 1-@Element79  (feel this way is so clever!)
```python3
class Solution:
    @lru_cache(None)
    def fib(self, n: int) -> int:
        return self.fib(n - 1) + self.fib(n -2) if n > 1 else n
```

## 2- Me
```python3
class Solution:
    def fib(self, n: int) -> int:
        if n==0:
            return 0
        elif n==1:
            return 1
        elif n>1 :
            res =self.fib(n-1)+self.fib(n-2)       
            return res
```         
---        
# Add Two Numbers
You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/add-two-numbers
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。

## (me)         
```python3
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution: 
    def addTwoNumbers(self, l1: ListNode, l2: ListNode) -> ListNode:
        temp_l1 = l1
        temp_l2 = l2
        count_l1 = 0
        count_l2 = 0
        num1 = 0
        num2 = 0

        while(temp_l1):
            num1 += pow(10, count_l1) * temp_l1.val
            count_l1 += 1
            temp_l1 = temp_l1.next

        while(temp_l2):
            num2 += pow(10, count_l2) * temp_l2.val
            count_l2 += 1
            temp_l2 = temp_l2.next    

        sum = num1 + num2
        def newNextNode(num):
                    if num >= 10:
                        new_num = num//10
                        Next = ListNode(num%10, newNextNode( new_num))
                    else:
                        Next = ListNode(num)
                    return Next   

        return newNextNode(sum)
```
         

           
             

          
    
             


          
    
             
           
            
        
