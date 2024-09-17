problem: https://leetcode.com/problems/merge-two-sorted-lists/

```cpp
class Solution {
public:
    ListNode* mergeTwoLists(ListNode* list1, ListNode* list2) {
        if(!list1) return list2;
        if(!list2) return list1;
        ListNode* ans = new ListNode();
        ListNode* head = ans;
        
        while(list1 && list2 ){
            if(list1->val < list2->val){
                head->next = list1;
                list1 = list1->next;
            }
            else {
                head->next = list2;
                list2 = list2->next;
            }
            head = head->next;
        }

        if(list1) head->next = list1;
        else head->next = list2;

        return ans->next;
    }
};
```
