Combination Sum II:
  Algorithm:
    i) implement subset construction
    ii) Skip the iteration if the consecutive element are same.
  Program:
    class Solution {
public:
    vector<vector<int>> ans;
    set<vector<int>>st;
    void solve(vector<int>& candidates,int target,int sum,vector<int>&temp,int i,int n)
    {
        if(target == 0)
        {
            st.insert(temp);
            return ;
        }
        if(i == n || target < 0)
        {
            return ;
        }
        temp.push_back(candidates[i]);
        solve(candidates,target-candidates[i],sum,temp,i+1,n);
        temp.pop_back();
        while (i + 1 < candidates.size() && candidates[i] == candidates[i + 1]) {
            i++;
        }
        solve(candidates,target,sum,temp,i+1,n);
        return ;
    }
    vector<vector<int>> combinationSum2(vector<int>& candidates, int target) {
        vector<int>temp;
        int n = candidates.size();
        // cout<<n<<"nis"<<endl;
        sort(candidates.begin(),candidates.end());
        solve(candidates,target,0,temp,0,n);
        for(auto& i : st)
        {
            ans.push_back(i);
        }
        return ans;
    }
};
