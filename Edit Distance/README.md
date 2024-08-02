Edit Distance:
  int n = str1.length();
        int m = str2.length();
        int dp[n+1][m+1];
        for(int i=0;i<=n;i++)
        {
            for(int j=0;j<=m;j++)
            {
                if(i == 0)
                {
                    dp[i][j] = j;
                }
                else if(j == 0)
                {
                    dp[i][j] = i;
                }
                else if(str1[i-1] == str2[j-1])
                {
                    dp[i][j] = dp[i-1][j-1];
                }
                else
                {
                    dp[i][j] = 1+min(dp[i][j-1], //insert
                                min(dp[i-1][j], //delete
                                dp[i-1][j-1])); //replace
                }
            }
        }
        // for(int i=0;i<=n;i++)
        // {
        //     for(int j=0;j<=m;j++)
        //     {
        //         cout<<dp[i][j]<<" ";
        //     }
        //     cout<<endl;
        // }
        return dp[n][m];
