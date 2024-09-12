Problem Statement : https://leetcode.com/problems/find-all-anagrams-in-a-string/

```cpp
class Solution {
public:
    vector<int> findAnagrams(string s, string p) {
        vector<int> ans;
        int f[26];
        for(char c : p){
            f[c - 'a']++;
        }
        int i=0, j=0;
        while(j < s.length()){
            f[s[j] - 'a']--;
            if(j >= p.size()-1){
                int sum = 0;
                for(int l=0; l<26; l++){
                    sum += abs(f[l]);
                }
                if(!sum){
                    ans.push_back(i);
                }
            }
            j++;
            if(j < p.size()) continue;
            f[s[i] - 'a']++;
            i++;
        }
        return ans;
    }
};
```
