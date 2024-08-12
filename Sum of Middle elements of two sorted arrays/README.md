Sum of Middle elements of two sorted arrays:

Program:
    int n = arr1.size();
        int m = arr2.size();
        int i=0,j=0;
        vector<int>ans;
        while(i < n && j < m)
        {
            if(arr1[i] < arr2[j])
            {
                ans.push_back(arr1[i]);
                i++;
            }
            else
            {
                ans.push_back(arr2[j]);
                j++;
            }
        }
        while(i < n)
        {
            ans.push_back(arr1[i]);
            i++;
        }
        while(j < n)
        {
            ans.push_back(arr2[j]);
            j++;
        }
        int mid1 = (n+m)/2 - 1,mid2 = (n+m)/2;
        int res = ans[mid1]+ans[mid2];
        return res;
