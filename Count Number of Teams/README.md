Count Number of Teams:

Program:
  int ans = 0;
        int n = rating.size();
        for(int i=0;i<n;i++)
        {
            int ls =0;
            int rs = 0;
            int lg = 0;
            int rg = 0;
            for(int j=i-1;j>=0;j--)
            {
                if(rating[j] < rating[i])
                {
                    ls++;
                }
                else if(rating[i] < rating[j])
                {
                    lg++;
                }
            }
            for(int j=i+1;j<rating.size();j++)
            {
                if(rating[j] < rating[i])
                {
                    rs++;
                }
                else if(rating[i] < rating[j])
                {
                    rg++;
                }
            }
            ans+=ls*rg;
            ans+=lg*rs;
        }
        return ans;
