Sum Tree:
  Algorithm:
    i)check every time root data with its left and right child
  Program:
    bool f = true;
    int postorder(Node* root)
    {
        if(!root)
            return 0;
        if(root->left == NULL && root->right == NULL)
        {
            return root->data;
        }
        int a = postorder(root->left);
        int b = postorder(root->right);
        if(root->data != a+b)
        {
            f = false;
        }
        root->data += a+b;
        return root->data;   
    }
    bool isSumTree(Node* root) {
        // Your code here
        int a = root->data;
        postorder(root);
        // cout<<root->data<<endl;
        if(f)
        {
            return true;
        }
        return false;
    }
