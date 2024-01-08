class Solution {
public:
    bool dfs(vector<int>& nums, vector<bool>& v, int target, int sum,int i, int k)
    {
        if(k==1)
            return true;
        if(i==nums.size())
            return false;
        if(sum==target)
            return dfs(nums, v, target, 0, 0, k-1);
        for(int j=i;j<nums.size();j++)
        {
            if(v[j] || sum+nums[j]>target)
                continue;
            v[j]=true;
            if(dfs(nums, v, target, sum+nums[j], j+1, k))
                return true;
            v[j]=false;
        }
        return false;
    }
    bool canPartitionKSubsets(vector<int>& nums, int k) {
        int sum=accumulate(nums.begin(), nums.end(), 0);
        if(nums.size()<k || sum%k)
            return false;
        sort(nums.begin(), nums.end(), greater<int>());
        vector<bool> v(nums.size(), false);
        bool ans=dfs(nums, v, sum/k, 0, 0, k);
        return ans;
    }
};
