Problem Statement : https://leetcode.com/problems/maximum-subarray/

```cpp
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int ans=INT_MIN, sum = 0;

        for(int i : nums){
            sum += i;
            ans = max(ans, sum);
            if(sum < 0) sum = 0;
        }
        
        return ans;
    }
};
```
