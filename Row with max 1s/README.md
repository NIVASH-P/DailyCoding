Row with max 1s:

Program:
  int ans = 0;
  vector<int>res;
  int n = arr.size();
  int m = arr[0].size();
  // cout<<n<<" "<<m<<endl;
  for(int i=0;i<m;i++)
  {
      for(int j=0;j<n;j++)
      {
          if(arr[j][i] == 1)
          {
              return j;
          }
      }
  }
  return -1;
