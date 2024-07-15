Smallest Number

Program:

  string smallestNumber(int s, int d) {
        // code here
        if(d*9 < s)
            return "-1";
        string ans = "";
        if(s == 1)
        {
            ans+='1';
            for(int i=1;i<d;i++)
            {
                ans+='0';
            }
            return ans;
        }
        for(int i=0;i<d;i++)
        {
            ans+='0';
        }
        for(int i=d-1;i>=0;i--)
        {
            if(s > 9)
            {
                ans[i]='9';
                s-=9;
            }
            else
            {
                if(i == 0)
                {
                    ans[i]=s+'0';
                }
                else if(s != 1)
                {
                    int a = (s-1);
                    ans[i]=a+'0';
                    s=1;
                }
            }
        }
        // reverse(ans.begin(),ans.end());
        return ans;
    }
