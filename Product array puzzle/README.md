Product array puzzle

Algorithm:
  vector<long long int> productExceptSelf(vector<long long int>& nums) {
        // code here
        vector<long long int>ans;
        long long int res = 1;
        bool f = 0;
        int c = 0;
        for(auto& i : nums)
        {
            if(i != 0)
            {
                res*=i;
            }
            else
            {
                f = 1;
                c++;
            }
        }
        if(f == 1 && c == 1)
        {
            for(auto& i : nums)
            {
                if(i == 0)
                {
                    // long long int a = res/i;
                    ans.push_back(res);
                }
                else
                {
                    ans.push_back(0);
                }
            }
        }
        else if(c > 1)
        {
            for(auto& i : nums)
            {
                ans.push_back(0);
            }
        }
        else
        {
            for(auto& i : nums)
            {
                long long int a = res/i;
                ans.push_back(a);
            }
        }
        return ans;
    }
