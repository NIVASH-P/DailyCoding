Algorithm:
  Easy Implemetaion like array .
  Consider Every row as a array.
  Make steps.

  Program:

  vector<vector<int>> rotateMatrix(int k, vector<vector<int>> mat) {
        // code here
        int n = mat.size();
        int m = mat[0].size();
        k = k%m;
        vector<vector<int>>ans(n,vector<int>(m,0));
        int st;
        for(int i=0;i<n;i++)
        {
            st = 0;
            for(int j=k;j<m;j++)
            {
                ans[i][st] = mat[i][j];
                st++;
            }
            for(int j=0;j<k;j++)
            {
                ans[i][st] = mat[i][j];
                st++;
            }
        }
        return ans;
    }
