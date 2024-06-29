All Ancestors of a Node in a Directed Acyclic Graph

Alogorihm:

  i)reverse the every node to head
  ii)done a bfs

Program:


void bfs(vector<vector<int>>& edges,vector<vector<int>>& ans,int st,int n)
    {
        queue<int>q;
        q.push(st);
        vector<int>v;
        vector<int>vis(n,0);
        vis[st] = 1;
        while(!q.empty())
        {
            int temp = q.front();
            q.pop();
            for(auto& i : edges[temp])
            {
                if(vis[i] == 0)
                {
                    v.push_back(i);
                    q.push(i);
                    vis[i] = 1;
                }
            }
        }
        sort(v.begin(),v.end());
        ans.push_back(v);
        return;
    }
    vector<vector<int>> getAncestors(int n, vector<vector<int>>& edges) {
        int m = edges.size();
        vector<vector<int>>e(n),ans;
        for(int i=0;i<m;i++)
        {
            e[edges[i][1]].push_back(edges[i][0]);
        }
        for(int i=0;i<n;i++)
        {
            bfs(e,ans,i,n);
        }
        return ans;
    }
