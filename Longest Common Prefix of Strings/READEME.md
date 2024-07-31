Longest Common Prefix of Strings:

Program:
  int n = INT_MAX;
  for(int i=0;i<arr.size();i++)
  {
      int m = arr[i].length();
      n = min(n,m);
  }
  string res = "";
  bool  f = false;
  for(int i=0;i<n;i++)
  {
      for(int j=1;j<arr.size();j++)
      {
          if(arr[0][i] != arr[j][i])
          {
              return res == "" ? "-1":res;
              break;
          }
      }
      // if(f)  break;
      res += arr[0][i];
  }
  return res;
