Sort the People

Algorithm:
  i) Sort According to height

Program:
  vector<string> sortPeople(vector<string>& names, vector<int>& heights) {
          vector<string> ans;
          vector<pair<int,string>>p;
          for(int i=0;i<names.size();i++)
          {
              p.push_back({heights[i],names[i]});
          }
          sort(p.begin(),p.end());
          for(auto& i : p)
          {
              ans.push_back(i.second);
          }
          reverse(ans.begin(),ans.end());
          return ans;
    }
