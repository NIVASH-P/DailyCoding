The Palindrome Pattern:

Algorithm:

  i)check every row and column is an palindrome.


Program:

bool ischeck(vector<int> temp)
    {
        int st = 0,end = temp.size()-1;
        while(st < end)
        {
            if(temp[st] != temp[end])
            {
                return false;
            }
            st++;
            end--;
        }
        return true;
    }
    string pattern(vector<vector<int>> &arr) {
        // Code Here
        int n = arr.size();
        int m = arr[0].size();
        string ans = "-1";
        for(int i=0;i<n;i++)
        {
            vector<int>temp;
            for(int j=0;j<m;j++)
            {
                // cout<<arr[i][j]<<" ";
                temp.push_back(arr[i][j]);
            }
            if(ischeck(temp))
            {
                ans = to_string(i);
                ans+= " R";
                return ans;
            }
            // cout<<endl;
        }
        for(int i=0;i<m;i++)
        {
            vector<int>temp;
            for(int j=0;j<n;j++)
            {
                temp.push_back(arr[j][i]);
            }
            if(ischeck(temp))
            {
                ans = to_string(i);
                ans+= " C";
                return ans;
            }
        }
        return ans;
    }
