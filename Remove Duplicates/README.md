Remove Duplicates
  unordered_map<char,int>mp;
        string ans = "";
        for(int i=0;i<str.length();i++)
        {
            mp[str[i]]++;
            if(mp[str[i]] == 1)
            {
                ans+=str[i];
            }
        }
        return ans;
