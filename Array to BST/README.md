Array to BST

Program:
  Node* preorder(int s ,int arr[],int e)
    {
        if(s > e)
        {
            return NULL;
        }
        int mid = (s+e)/2;
        Node* newnode = new Node(arr[mid]);
        newnode->left = preorder(s,arr,mid-1);
        newnode->right = preorder(mid+1,arr,e);
        return newnode;
    }
    Node* sortedArrayToBST(vector<int>& nums) {
        // Code here
        int n = nums.size();
        int arr[n];
        int j = 0;
        for(auto& i : nums)
        {
            arr[j] = i;
            j++;
        }
        return preorder(0,arr,n-1);
    }
