Merge Nodes in Between Zeros

Program:

  ListNode* mergeNodes(ListNode* head) {
        ListNode* temp = head->next;
        vector<int>v;
        int sum = 0;
        while(temp != NULL)
        {
            if(temp->val == 0)
            {
                v.push_back(sum);
                sum = 0;
            }
            sum+=temp->val;
            temp = temp->next;
        }
        ListNode* pretemp = NULL;
        temp = head;
        for(auto& i : v)
        {
            pretemp = temp;
            temp->val = i;
            temp = temp->next;
            cout<<i<<endl;
        }
        pretemp->next = NULL;
        return head;
    }
