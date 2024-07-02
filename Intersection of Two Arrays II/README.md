Intersection of Two Arrays II

Program:

vector<int> intersect(vector<int>& num1, vector<int>& num2) {
        map<int,int>mp;
        vector<int>ans;
        for(auto& i : num1)
        {
            mp[i]++;
        }
        for(auto& i : num2)
        {
            if(mp[i] > 0)
            {
                ans.push_back(i);
                mp[i]--;
            }
        }
        return ans;
    }
