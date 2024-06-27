Toeplitz matrix

Algorithm:
  i)Check every element with its previous element.


Program:

bool isToeplitz(vector<vector<int>>& mat) {
    // code here
    int n = mat.size();
    int m=mat[0].size();
    if(n == 1 || m == 1)
    {
        return true;
    }
    int a = mat[0][0];
    bool ans = true;
    for(int i=0;i<n;i++)
    {
        for(int j=0;j<m;j++)
        {
            if(i > 0 && j > 0)
            {
                if(mat[i][j] != mat[i-1][j-1])
                {
                    return false;
                }
            }
        }
    }
    return true;
}
