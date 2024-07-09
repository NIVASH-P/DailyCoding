Closest Three Sum


Program:

  int threeSumClosest(vector<int> arr, int target) {
        // Your code goes here
        sort(arr.begin(),arr.end());
        vector<int>a;
        int ans = 0;
        int n = arr.size();
        int mini = INT_MAX;
        for(int i=0;i<n-2;i++)
        {
            int j = i+1 , k = n-1;
            while(j < k)
            {
                int sum = arr[i]+arr[j]+arr[k];
                if(sum == target)
                {
                    // cout<<1<<endl;
                    return sum;
                }
                int diff = abs(sum-target);
                a.push_back(sum);
                // cout<<diff<<endl;
                if(mini >= diff)
                {
                    mini = diff;
                }
                if(sum < target)
                {
                    j++;
                }
                else
                {
                    k--;
                }
            }
        }
        int temp = mini+target;
        for(auto& i : a)
        {
            if(i == temp)
            {
                return temp;
            }
        }
        // cout<<mini<<" "<<target<<endl;
        return target-mini;
    }
