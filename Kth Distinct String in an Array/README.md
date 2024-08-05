Kth Distinct String in an Array:

Program:
  string kthDistinct(vector<string>& arr, int k) {
        string ans = "";
        int n = arr.size();
        unordered_map<string,int>mp;
        for(int i=0;i<n;i++)
        {
            mp[arr[i]]++;
        }
        for(int i=0;i<n;i++)
        {
            if(mp[arr[i]] == 1)
            {
                k--;
            }
            if(k == 0)
            {
                ans = arr[i];
                break;
            }
        }
        return ans;
