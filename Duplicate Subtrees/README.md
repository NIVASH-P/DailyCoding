Duplicate Subtrees

  ALGORITHM:
    i)store the every node in the string.
    ii)compare the sub tree with the String
PROGRAM:
  unordered_map<string,int>mp;
    vector<Node*>ans;
    string solve(Node* root)
    {
        if(!root)
            return "0";
        string temp = "";
        string l = solve(root->left);
        string r = solve(root->right);
        temp =l+r+to_string(root->data);
        if(mp[temp] == 1)
        {
            ans.push_back(root);
        }
        mp[temp]++;
        return temp;    
    }
    vector<Node*> printAllDups(Node* root) {
        // Code here
        solve(root);
        return ans;
    }
