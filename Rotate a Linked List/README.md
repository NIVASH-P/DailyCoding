Rotate a Linked List:

  Program:
    Node* rotate(Node* head, int k) {
        // Your code here
        vector<int>v;
        Node* temp = head;
        int n = 0;
        while(temp!= NULL)
        {
            temp = temp->next;
            n++;
        }
        k = k%n;
        temp = head;
        int i = 0;
        while(i < k)
        {
            v.push_back(temp->data);
            temp=temp->next;
            i++;
        }
        head = temp;
        while(temp->next != NULL)
        {
            temp = temp->next;
        }
        for(auto& i : v)
        {
            Node* newnode = new Node(i);
            temp->next = newnode;
            temp=temp->next;
        }
        return head;
    }
