Bottom View of Binary Tree

Algorithm:
  i) Horizontal Distance
  vector <int> bottomView(Node *root) {
        // Your Code Here
        vector<int>ans;
        // unordered_map<int,int>mp1;
        map<int,int>mp;
        queue<pair<int,Node*>>q;
        mp[0] = root->data;
        // mp2[0] = root->data;
        q.push({0,root});
        int l = INT_MAX;
        int h = INT_MIN;
        while(!q.empty())
        {
            pair<int,Node*> p = q.front();
            q.pop();
            int hd = p.first;
            Node* temp = p.second;
            mp[hd] = temp->data;
            if(temp->left != NULL)
            {
                q.push({hd-1,temp->left});
            }
            if(temp->right != NULL)
            {
                
                q.push({hd+1,temp->right});
            }
            
        }
        for(auto& i : mp)
        {
            ans.push_back(i.second);
        }
        return ans;
    }
