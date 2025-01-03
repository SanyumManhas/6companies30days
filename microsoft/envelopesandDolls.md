### TC-> O(nlogn + n)
### SC-> O(n)

###Solution 
```cpp
class Solution {
public:
    int maxEnvelopes(vector<vector<int>>& E) {
        sort(E.begin(), E.end(), [](vector<int>& a, vector<int>& b) 
             -> bool {return a[0] == b[0] ? b[1] < a[1] : a[0] < b[0];});
        vector<int> dp;
        for (auto& env : E) {
            int height = env[1];
            int left = lower_bound(dp.begin(), dp.end(), height) - dp.begin();
            if (left == dp.size()) dp.push_back(height);
            dp[left] = height;
        }
        return dp.size();
    }
};
```

###Screenshots
![Q3](https://github.com/user-attachments/assets/08a6f704-2457-4d27-9a4d-74c9dbb38008)
![5](https://github.com/user-attachments/assets/e85d5ea2-6cb2-4b39-9407-8c7efead85c9)
