problem statement : https://leetcode.com/problems/product-of-array-except-self/

```cpp
class Solution {
public:
    vector<int> productExceptSelf(vector<int>& nums) {
        int n = nums.size();
        vector<int> ans(n,1);

        int pm=1, sm = 1;

        for(int i=0; i<n; i++){
            ans[i] *= pm;
            pm *= nums[i];
            ans[n - i -1] *= sm;
            sm *= nums[n - i -1] ;
        }
        return ans;
    }
};
```
