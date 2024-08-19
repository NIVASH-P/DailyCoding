2 Keys Keyboard
  i)power calculation

Program:
  int minSteps(int n) {
        int ans = 0;
        int i =0;
        int f = 2;
        while(n > 1)
        {
            while(n%f == 0)
            {
                n/=f;
                ans+=f;
            }
            f++;
        }
        return ans;
    }
