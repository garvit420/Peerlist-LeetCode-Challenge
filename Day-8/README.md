problem: https://leetcode.com/problems/reverse-linked-list/

```cpp
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        ListNode* prev = NULL;
        ListNode* curr = head;
        while(head != NULL){
            head = head->next;
            curr->next = prev;
            prev = curr;
            curr = head;
        }
        return prev;
    }
};
```
