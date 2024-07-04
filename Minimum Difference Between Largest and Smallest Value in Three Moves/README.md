Minimum Difference Between Largest and Smallest Value in Three Moves

Algorithm:

  i)select 1st and third value
  ii)select 2nd and second value
  iii)select 3nd and first value
  iv)select third and last value

Program:

int minDifference(vector<int>& nums) {
        int n = nums.size();
        if(n <= 4)
        {
            return 0;
        }
        sort(nums.begin(),nums.end());
        int ans = INT_MAX;
        ans =min(ans,nums[n-4]-nums[0]);
        ans =min(ans,nums[n-1]-nums[3]);
        ans =min(ans,nums[n-3]-nums[1]);
        ans =min(ans,nums[n-2]-nums[2]);
        return ans;
    }