Lucky Number

Program:
  vector<int> luckyNumbers (vector<vector<int>>& matrix) {
        vector<int>ans;
        int n = matrix.size();
        int m = matrix[0].size();
        int row[n][m];
        int col[n][m];
        for(int i=0;i<m;i++)
        {
            int maxi =  INT_MIN;
            for(int j=0;j<n;j++)
            {
                maxi = max(matrix[j][i],maxi);
            }
            for(int j=0;j<n;j++)
            {
                row[j][i] = maxi;
                // cout<<row[j][i]<<" ";
            }
            // cout<<endl;
        }
        for(int i=0;i<n;i++)
        {
            int mini =  INT_MAX;
            for(int j=0;j<m;j++)
            {
                mini = min(matrix[i][j],mini);
            }
            for(int j=0;j<m;j++)
            {
                col[i][j] = mini;
                // cout<<row[j][i]<<" ";
            }
            // cout<<endl;
        }
        for(int i=0;i<n;i++)
        {
            for(int j=0;j<m;j++)
            {
                if(row[i][j] == col[i][j])
                {
                    ans.push_back(row[i][j]);
                }
            }
            // cout<<endl;
        }
        return ans;;
    }
