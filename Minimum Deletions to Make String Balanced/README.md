Minimum Deletions to Make String Balanced
  Program:
      int minimumDeletions(string s) {
        int n = s.length();
        int ans = 0,a_c = 0;
        for(int i = s.length()-1;i>=0;i--)
        {
            if(s[i] == 'a')
            {
                a_c++;
            }
            else
                ans = min(ans+1,a_c);
        }
        return ans;
        
    }
