Largest square formed in a matrix

Algorithm :
  I)Use Dp Approach

Program:
  static int maxSquare(int n, int m, int mat[][]) {
        // code here
        int sqr_mat[][] = new int[n][m];
        for(int i=0;i<n;i++)
        {
            sqr_mat[i][0]=mat[i][0];
        }
        for(int i=0;i<m;i++)
        {
            sqr_mat[0][i]=mat[0][i];
        }
        for(int i=1;i<n;i++)
        {
            for(int j=1;j<m;j++)
            {
                if(mat[i][j] == 1)
                {
                    // cout<<mat[i-1][j]<<" "<<mat[i-1][j-1]<<" "<<mat[i][j-1]<<endl;
                    // System.out.print(sqr_mat[i-1][j]+" "+sqr_mat[i-1][j-1]+" "+sqr_mat[i][j-1]);
                    sqr_mat[i][j] = 1+Math.min(sqr_mat[i-1][j],Math.min(sqr_mat[i-1][j-1],sqr_mat[i][j-1]));
                }
                else
                    sqr_mat[i][j] = 0;
                // System.out.println(sqr_mat[i][j]);        
            }
        }
        int ans = 0;
        for(int i=0;i<n;i++)
        {
            for(int j=0;j<m;j++)
            {
                // System.out.print(sqr_mat[i][j]+" ");
                ans = Math.max(ans,sqr_mat[i][j]);
            }
            // System.out.println();
            // cout<<endl;
        }
        return ans;
