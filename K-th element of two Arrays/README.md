K-th element of two Arrays:

  Program:
    int i =0,j=0,n = arr1.size(),m=arr2.size();
        int c = 0;
        int res = 0;
        vector<int>v;
        while(i < n && j < m)
        {
            if(arr1[i] < arr2[j])
            {
                // res = arr1[i];
                v.push_back(arr1[i]);
                i++;
            }
            else
            {
                res = arr2[j];
                v.push_back(arr2[j]);
                j++;
            }
            // c++;
        }
        while(i < n)
        {
            v.push_back(arr1[i]);
            i++;
        }
        while(j < m)
        {
            v.push_back(arr2[j]);
            j++;
        }
        return v[k-1];
