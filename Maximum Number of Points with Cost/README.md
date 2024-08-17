Maximum Number of Points with Cost:
  Algorithm:
    i) Use Dp.
    ii)At Every time fint left max,right max to find 
  class Solution {
  public:
      long long maxPoints(vector<vector<int>>& points) {
          long long ans = 0;
          int n = points.size();
          int m = points[0].size();
          int dp[n][m]; 
          vector<long long>v(points[0].begin(),points[0].end());
          for(int i=1;i<n;i++)
          {
              vector<long long> left(m),right(m);
              left[0] = v[0];
              for(int j=1;j<m;j++)
              {
                  left[j] = max(left[j-1]-1,v[j]);
              }
              right[m-1] = v[m-1];
              for(int j=m-2;j>=0;j--)
              {
                  right[j] = max(right[j+1]-1,v[j]);
              }
              for(int j=0;j<m;j++)
              {
                  v[j] = points[i][j]+max(right[j],left[j]);
              }
          }
          long long res = 0;
          for(int i=0;i<m;i++)
          {
              if(res < v[i])
              {
                  res = v[i];
              }
          }
          return res;
      }
  };
