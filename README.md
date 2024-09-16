# Remove-Duplicates-from-Sorted-List

Given the head of a sorted linked list, delete all duplicates such that each element appears only once. Return the linked list sorted as well.
Constraints:
The number of nodes in the list is in the range [0, 300].
-100 <= Node.val <= 100
The list is guaranteed to be sorted in ascending order.

class Solution:
    def deleteDuplicates(self, head: ListNode) -> ListNode:
        if not head:
            return None
        
        temp = head
        temp2 = head.next
        last = head.val
        
        while temp2:  
            if temp2.val == last:  
                if not temp2.next:  
                    temp.next = None
                    break
                temp2 = temp2.next  
                temp.next = temp2 
            else:  
                temp = temp2
                last = temp.val
                temp2 = temp2.next
        
        return head  
