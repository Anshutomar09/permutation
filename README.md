# permutation

class Solution {
public:
    void solve(vector<int>&nums, vector<vector<int>>&ans, int ind){
        if(ind>=nums.size()){//base condition when index is larger than the size of array
            ans.push_back(nums);
            return;
        }
        for(int i=ind;i<nums.size();i++){
            swap(nums[ind], nums[i]);//swaping the other elements then the first index
            solve(nums, ans, ind+1);//calling function again for changing the index
            swap(nums[ind], nums[i]);
        }
    }
    vector<vector<int>> permute(vector<int>& nums) {
        vector<vector<int>>ans;
        solve(nums, ans, 0);
        return ans;
    }
};
