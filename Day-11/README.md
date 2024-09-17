problem: https://leetcode.com/problems/remove-nth-node-from-end-of-list/

```cpp
class Solution {
public:
    ListNode* removeNthFromEnd(ListNode* head, int n) {
        int sz = 0;
        ListNode* curr = head;
        while(curr){
            sz++;
            curr = curr->next;
        }
        n = sz - n;
        if(n == 0){
            return head->next;
        }
        curr = head;
        ListNode* prev = NULL;
        while(n > 0){
            prev = curr;
            curr = curr->next;
            n--;
        }
        if(prev && prev->next) {
            prev->next = prev->next->next;
        }   
        return head;
    }
};
```
