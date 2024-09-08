Problem Statement : https://leetcode.com/problems/best-time-to-buy-and-sell-stock/

```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int mn = prices[0], ans = 0;

        for(int p : prices){
            mn = min(mn, p);
            ans = max(ans, p - mn);
        }

        return ans;
    }
};
```
