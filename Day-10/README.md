problem: https://leetcode.com/problems/middle-of-the-linked-list/

```cpp
class Solution {
public:
    ListNode* middleNode(ListNode* head) {
        ListNode* s = head;

        while(head && head->next){
            head = head->next->next;
            s = s->next;
        }

        return s;
    }
};
```
