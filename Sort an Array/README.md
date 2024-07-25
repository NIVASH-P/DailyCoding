Sort an Array

Program:
  class Solution {
public:
    void merge(vector<int>& nums,int l,int mid,int h)
    {
        // int left[mid-l+1];
        // int right[h-mid];
        // int left_n = mid-l+1;
        // int right_n = h-mid;
        // for(int i=0;i<left_n;i++)
        // {
        //     left[i] = nums[l+i];
        //     cout<<left[i]<<" ";
        // }
        // cout<<endl;
        // for(int i=0;i<right_n;i++)
        // {
        //     right[i] = nums[mid+i+1];
        //     cout<<right[i]<<" ";
        // }
        // cout<<endl;
        vector<int> temp;
        int i = l, j = mid+1;
        int k = l;
        while(i <= mid && j <= h )
        {
            if(nums[i] <= nums[j])
            {
                temp.push_back(nums[i++]);
            }
            else
            {
                temp.push_back(nums[j++]);
            }
        }
        while(i <= mid)
        {
            temp.push_back(nums[i++]);
        }
        while(j <= h)
        {
           temp.push_back(nums[j++]);
        }
        for(int i=l;i<=h;i++){
            nums[i]=temp[i-l];
        }
    }
    void mergeSort(vector<int>& nums,int l,int h)
    {
        if(l >= h)
        {
            return ;
        }
        int mid = l+(h-l)/2;
        mergeSort(nums,l,mid);
        mergeSort(nums,mid+1,h);
        merge(nums,l,mid,h);
    }
    vector<int> sortArray(vector<int>& nums) {
        mergeSort(nums,0,nums.size()-1);
        return nums;
    }
};
