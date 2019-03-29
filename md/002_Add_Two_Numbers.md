You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

Example:

Input: (2 -> 4 -> 3) + (5 -> 6 -> 4)
Output: 7 -> 0 -> 8
Explanation: 342 + 465 = 807.

```
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
    let sum = 0;
    let newNode = new ListNode(0),// 保留初始节点 返回newNode.next
        resNode = newNode,
        p1 = l1,
        p2 = l2;
    while(p1 != null || p2 != null){
        if(p1 != null){
            sum = sum + p1.val;
            p1 = p1.next;
        }
        if(p2 != null){
            sum = sum + p2.val;
            p2 = p2.next;
        }
        resNode.next = new ListNode(sum%10);
        
        sum = Math.floor(sum/10);//js整除需要用那个Math.floor
        resNode = resNode.next;
    }
    
    if(sum != 0) resNode.next = new ListNode(sum); //如果最后一位需要进位，再加一个节点

    return newNode.next;//返回newNode的next，因为此时resNode已经是最后一个节点了
};
```
