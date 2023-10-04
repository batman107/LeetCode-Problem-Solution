68. Question- Top K frequent Elements

    Solution-

#include <vector>
#include <unordered_map>
#include <queue>

using namespace std;

class Solution {
public:
    vector<int> topKFrequent(vector<int> &nums, int k) {
        unordered_map<int, int> mp;
        priority_queue<pair<int, int>> pq;

        for (auto i : nums) {
            mp[i]++;
        }

        nums.clear();
        for (auto i : mp) {
            pq.push({i.second, i.first});
        }

        for (int i = 0; i < k; i++) {
            nums.push_back(pq.top().second);
            pq.pop();
        }

        return nums;
    }
};


The time complexity of the above code is O(n log n).
The space complexity of the above code is O(n).
