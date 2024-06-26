Balance a Binary Search Tree

Algorithm:

  i)Convert the tree into array.
  ii)Built new array
    with middle element as root
    It make a balanced BST

Program:

class Solution {
public:
    void inorder(vector<int>&ans,TreeNode* root)
    {
        if(root == NULL)
            return ;
        inorder(ans,root->left);
        ans.push_back(root->val);
        inorder(ans,root->right);
    }
    TreeNode* builtTree(int l,int h,vector<int>ans)
    {
        if(l > h)
        {
            return NULL;
        }
        int mid = (l+h)/2;
        TreeNode *root = new TreeNode(ans[mid]);
        root->left = builtTree(l,mid-1,ans);
        root->right = builtTree(mid+1,h,ans);
        return root;
    }
    TreeNode* balanceBST(TreeNode* root) {
        vector<int>ans;
        inorder(ans,root);
        return builtTree(0,ans.size()-1,ans);
    }
};
