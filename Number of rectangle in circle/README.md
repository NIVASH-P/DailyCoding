class Solution {
  public:
    int rectanglesInCircle(int r) {
        // code here
        int count = 0;
        for(int i=1;i<=2*r;i++)
        {
            for(int j=1;j<=2*r;j++)
            {
                if(pow(i,2) <= 4*r*r - pow(j,2))
                {
                    count++;
                }
            }
        }
        return count;
    }
};
