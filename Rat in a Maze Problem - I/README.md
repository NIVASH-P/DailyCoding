Rat in a Maze Problem - I
Program:
  vector<string>ans;
    int n;
    bool ischeck(vector<vector<int>> &mat,int i,int j,vector<vector<int>>&vis)
    {
        if(i>=0 && j>=0&&i<n&&j<n&&mat[i][j] == 1 && vis[i][j] == 0)
        {
            return true;
        }
        return false;
    }
    void solve(vector<vector<int>> &mat,int i,int j,string s,vector<vector<int>>&vis)
    {
        if(i > n-1 || j > n-1 || i < 0 || j < 0)
        {
            return ;
        }
        if(i == n-1 && j == n-1)
        {
            ans.push_back(s);
            return ;
        }
        if(ischeck(mat,i,j,vis))
        {
            vis[i][j] = 1;
            solve(mat,i+1,j,s+'D',vis);
            solve(mat,i,j+1,s+'R',vis);
            solve(mat,i,j-1,s+'L',vis);
            solve(mat,i-1,j,s+'U',vis);
            vis[i][j] = 0;
        }
        return ;
    }
    vector<string> findPath(vector<vector<int>> &mat) {
        // Your code goes here
        n = mat.size();
        vector<vector<int>>vis(n);
        for(int i=0;i<n;i++)
        {
            vis[i] = vector<int>(n,0);
        }
        if(mat[n-1][n-1] == 0)
        {
            return ans;
        }
        solve(mat,0,0,"",vis);
        return ans;
    }
