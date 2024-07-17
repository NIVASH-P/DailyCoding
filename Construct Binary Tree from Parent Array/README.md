Construct Binary Tree from Parent Array


Algorithm:

  i)Your Code
  
Program
  Node *createTree(vector<int> parent) {
        // Your code here
        map<int,Node*>mp;
        map<int,int>val_in;
        for(int i=0;i<parent.size();i++)
        {
            mp[i]=new Node(i);
        }
        int ans = -1;
        // cout<<mp[0]<<endl;
        int n_c = 0;
        for(auto& i : parent)
        {
            if(i == -1)
            {
                ans = n_c;
            }
            else
            {
                Node* temp = mp[i];
                if(temp->left == NULL)
                {
                    temp->left = mp[n_c];
                }
                else
                {
                    temp->right = mp[n_c];
                }
            }
            n_c++;
        }
        return mp[ans];
    }
