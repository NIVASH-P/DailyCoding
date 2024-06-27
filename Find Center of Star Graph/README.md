Find Center of Star Graph:

Algorithm:
  i)count the every node , if one node is present in all vertices
  ii) Return node value.

Program:

class Solution {
public:
    int findCenter(vector<vector<int>>& edges) {
        map<int,int>mp;
        for(int i=0;i<edges.size();i++)
        {
            for(int j=0;j<2;j++)
            {
                mp[edges[i][j]]++;
            }
        }
        for(auto& i : mp)
        {
            if(i.second == edges.size())
            {
                return i.first;
            }
        }
        return -1;
    }
};
