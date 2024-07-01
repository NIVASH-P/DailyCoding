Make Binary Tree From Linked List


Algorithm:

  i)Implement the binary Tree using queue


Program:

  void convert(Node *head, TreeNode *&root) {
    Node* temp = head;
    queue<TreeNode*>q;
    root = new TreeNode(head->data);
    q.push(root);
    head = head->next;
    while(head != NULL)
    {
        TreeNode* t = q.front();
        q.pop();
        if(head != NULL)
        {
            t->left = new TreeNode(head->data);
            q.push(t->left);
            head = head->next;
        }
        if(head != NULL)
        {
            t->right = new TreeNode(head->data);
            q.push(t->right);
            head = head->next;
        } 
    }
    return ;
}
