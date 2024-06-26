Container With Most Water

Algorithm:
  Two Pointer Algorithm

Program:

class Solution {
public:
    int maxArea(vector<int>& height) {
        int n = height.size();
        int left[n];
        int right[n];
        left[0]=height[0];
        for(int i=1;i<n;i++)
        {
            left[i]=max(left[i-1],height[i]);
        }
        right[n-1]=height[n-1];
        for(int i=n-2;i>=0;i--)
        {
            right[i]=max(right[i+1],height[i]);
        }
        int i = 0,j = n-1;
        int ans = 0;
        while(i<j)
        {
            int a = min(left[i],right[j]);
            if(ans < a*(j-i))
            {
                cout<<a<<" "<<j-i<<endl;
                ans=a*(j-i);
            }
            if(left[i]<right[j])
            {
                i++;
            }
            else
            {
                j--;
            }
        }
        return ans;
    }
};
