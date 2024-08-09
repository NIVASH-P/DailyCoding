Magic Squares In Grid:
  Algorithm:
    i)take every middle element and take 3 X 3 matrix
    ii)find row,col,diagonal sum
    iii)using set to delete all the present items
  Program:
    class Solution {
public:
    bool ismagiccube(int i,int j,vector<vector<int>>& grid)
    {
        int row1 = grid[i-1][j-1]+grid[i][j-1]+grid[i+1][j-1];
        int row2 = grid[i-1][j]+grid[i][j]+grid[i+1][j];
        int row3 = grid[i-1][j+1]+grid[i][j+1]+grid[i+1][j+1];
        int col1 = grid[i-1][j-1]+grid[i-1][j]+grid[i-1][j+1];
        int col2 = grid[i][j-1]+grid[i][j]+grid[i][j+1];
        int col3 = grid[i+1][j-1]+grid[i+1][j]+grid[i+1][j+1];
        int d1 = grid[i-1][j-1]+grid[i][j]+grid[i+1][j+1];
        int d2 = grid[i-1][j+1]+grid[i][j]+grid[i+1][j-1];
        cout<<row1<<" "<<row2<<" "<<row3<<" "<<col1<<" "<<col2<<" "<<col3<<" "<<d1<<" "<<d2<<endl;
        if((row1 == row2) && (row2 == row3 )&& (row3 == col1) && (col1 == col2) && (col2 == col3) && (col3 == d1) && (d1 == d2))
        {
            set<int>st{1,2,3,4,5,6,7,8,9};
            st.erase(grid[i-1][j-1]);
            st.erase(grid[i][j-1]);
            st.erase(grid[i+1][j-1]);
            st.erase(grid[i-1][j]);
            st.erase(grid[i][j]);
            st.erase(grid[i+1][j]);
            st.erase(grid[i-1][j+1]);
            st.erase(grid[i][j+1]);
            st.erase(grid[i+1][j+1]);
            if(st.empty())
            {
                return true;
            }
            return false;
        }
        return false;
    }
    int numMagicSquaresInside(vector<vector<int>>& grid) {
        int n,m;
        n = grid.size();
        m = grid[0].size();
        int res = 0;
        for(int i=1;i<n-1;i++)
        {
            for(int j=1;j<m-1;j++)
            {
                if(ismagiccube(i,j,grid))
                {
                    res++;
                }
            }
        }
        return res;
    }
        
};
