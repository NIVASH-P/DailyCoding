Longest alternating subsequence:

Algorithm:
  i)count up and down
  ii)change up and down & viceversa
Program:
  int alternatingMaxLength(vector<int>& arr) {
        int up = 1,down = 1;
        for(int i=1;i<arr.size();i++)
        {
            if(arr[i-1] < arr[i])
            {
                up = down+1;
            }
            else if(arr[i-1] > arr[i])
            {
                down = up+1;
            }
        }
        int ans = max(up,down);
        return ans;
        
    }
