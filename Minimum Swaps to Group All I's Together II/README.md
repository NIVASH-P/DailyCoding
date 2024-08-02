Minimum Swaps to Group All I's Together II:

Program : (Sliding Window)
  int ans = 0,o_c = 0;
        int n = nums.size();
        for(auto& i : nums)
        {
            if(i == 1)
            {
                o_c++;
            }
        }
        int sum = 0;
        for(int i=0;i<o_c;i++)
        {
            sum+=nums[i];
        }
        int res = o_c-sum;
        for(int i=1;i<=n;i++)
        {
            sum-=nums[i-1];
            sum+=nums[(i+o_c-1)%n];
            int swap = o_c-sum;
            res = min(res,swap);
            cout<<swap<<" "<<res<<endl;
        }
        return res;
