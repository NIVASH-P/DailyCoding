Maximum Total Importance of Roads

Algorithm:

  i)get the frequency and assign the values based on descending order of prioriy.
  ii)do the given step

Program:


long long maximumImportance(int n, vector<vector<int>>& roads) {
        map<int,int>mp;
        for(int i=0;i<roads.size();i++)
        {
            mp[roads[i][0]]++;
            mp[roads[i][1]]++;
        }
        vector<pair<int,int>>cities;
        for(const auto& i : mp)
        {
            cities.push_back(i);
        }
        sort(cities.begin() , cities.end() , [](auto& a,auto& b){
            return a.first>b.first;
        });
        sort(cities.begin() , cities.end() , [](auto& a,auto& b){
            return a.second>b.second;
        });
        int cit[n];
        int temp=n;
        for(const auto& i : cities)
        {
            cout<<i.first<<" "<<i.second<<endl;
            cit[i.first] = temp;
            temp--;
        }
        for(const auto& i : cit)
        {
            cout<<i<<endl;
        }
        long long ans  = 0;
        for(int i=0;i<roads.size();i++)
        {
            ans+=(cit[roads[i][0]]+cit[roads[i][1]]);
        }
        return ans;
    }
