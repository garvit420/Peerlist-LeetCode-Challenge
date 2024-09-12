problem: https://leetcode.com/problems/group-anagrams/description/

```cpp
class Solution {
public:
    vector<vector<string>> groupAnagrams(vector<string>& strs) {
        unordered_map<string, int> map;
        vector<vector<string>> ans;

        for(string s : strs){
            string o = s;
            sort(s.begin(), s.end());
            if(map.find(s) == map.end()){
                map[s] = ans.size();
                ans.push_back( vector<string>());
            }
            ans[map[s]].push_back(o);
        } 
        cout << strs[0];
        return ans;
    }
};
```
