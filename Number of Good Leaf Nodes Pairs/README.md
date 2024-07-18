Number of Good Leaf Nodes Pairs

Algorithm:
  i)store the left and right vectors
  ii)check the sum of variables is less than d

Program:

  vector<int>ans;
    int d,res = 0;
    vector<int> solve(TreeNode* root)
    {
        cout<<d<<endl;
        if(!root)
            return {};
        if(root->left == NULL &&  root->right == NULL)
        {
            return {1};
        }
        vector<int> left = solve(root->left);
        vector<int> right = solve(root->right);
        for(auto& l : left)
        {
            for(auto& r : right)
            {
                if(l+r <= d)
                {
                    res++;
                }
            }
        }
        vector<int>curr;
        for(auto& i : left)
        {
            if(i+1 <= d)
            {
                curr.push_back(i+1);
            }
        }
        for(auto& i : right)
        {
            if(i+1 <= d)
            {
                curr.push_back(i+1);
            }
        }
        return curr;
    }
    int countPairs(TreeNode* root, int distance) {
        d = distance;
        solve(root);
        return res;
    }
