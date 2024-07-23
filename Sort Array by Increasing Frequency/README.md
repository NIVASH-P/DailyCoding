Sort Array by Increasing Frequency

  Algorithm:
    i) Use Custom sort
  Program:
    bool cmp(const pair<int,int>& a ,const pair<int,int>& b)
    {
        if(a.first > b.first)
        {
            return true;
        }
        else if(a.first == b.first)
        {
            if(a.second < b.second)
            {
                return true;
            }
            return false;
        }
        return false;
    }
    vector<int> frequencySort(vector<int>& nums) {
        vector<int>ans;
        unordered_map<int,int>mp;
        // sort(nums.begin(),nums.end(),greater<int>());
        for(auto& i : nums)
        {
            mp[i]++;
        }
        vector<pair<int,int>>p;
        for(auto& i : mp)
        {
            cout<<i.first<<" ";
            p.push_back({i.second,i.first});
        }
        sort(p.begin(),p.end(),[this](const pair<int,int>& a,const pair<int,int>& b){
            return this->cmp(a,b);
        });
        for(auto& i : p)
        {
            for(int j=0;j<i.first;j++)
            {
                ans.push_back(i.second);
            }
        }
        reverse(ans.begin(),ans.end());
        return ans;
    }
