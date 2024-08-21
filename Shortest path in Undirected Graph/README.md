Shortest path in Undirected Graph
  Algorithm:
    i)At first mark every given node value travel distance
    ii)Convert the every node of directional node is increment by 1
  Program:
    vector<vector<int>>gp(n);
        for(auto& i : edges)
        {
            gp[i[0]].push_back(i[1]);
            gp[i[1]].push_back(i[0]);
        }
        vector<int>ans(n,-1);
        queue<int>q;
        ans[src] = 0;
        q.push(src);
        while(!q.empty())
        {
            int a = q.front();
            q.pop();
            for(auto& i : gp[a])
            {
                // cout<<i<<" ";
                if(ans[i] == -1)
                {
                    ans[i] = ans[a]+1;
                    q.push(i);
                }
                // for(int i=0;i<n;i++)
                // {
                //     cout<<ans[i]<<" ";
                // }
                // cout<<endl;
            }
        }
        return ans;
