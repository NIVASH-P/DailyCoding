Coverage of all Zeros in a Binary Matrix


coverage for a particular 0 is defined as a total number of ones around a zero in left, right, up and bottom directions.



Algorithm:
  i)Start with every zero
  ii)implement base case to check the sorroundance of one

Program:


int findCoverage(vector<vector<int>>& matrix) {
        // Code here
        int ans = 0;
        int n = matrix.size();
        int m = matrix[0].size();
        for(int i=0;i<n;i++)
        {
            for(int j=0;j<m;j++)
            {
                if(matrix[i][j] == 0)
                {
                    if(i > 0 && matrix[i-1][j] == 1)
                    {
                        ans++;
                        // cout<<i<<" "<<j<<" "<<ans<<endl;
                    }
                    if(j > 0 && matrix[i][j-1] == 1)
                    {
                        ans++;
                        // cout<<i<<" "<<j<<" "<<ans<<endl;
                    }
                    if(i < n-1 && matrix[i+1][j] == 1)
                    {
                        ans++;
                        // cout<<i<<" "<<j<<" "<<ans<<endl;
                    }
                    if(j < m-1 && matrix[i][j+1] == 1)
                    {
                        ans++;
                        // cout<<i<<" "<<j<<" "<<ans<<endl;
                    }
                }
            }
        }
        return ans;
    }
