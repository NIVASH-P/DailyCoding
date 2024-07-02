linked list of strings forms a palindrome

Program:

  bool ispalin(string str)
    {
        int st = 0,end = str.length()-1;
        while(st < end)
        {
            if(str[st] != str[end])
            {
                return false;
            }
            st++;
            end--;
        }
        return true;
    }
    bool compute(Node* head) {
        // Your code goes here
        string str = "";
        while(head != NULL)
        {
            str+=head->data;
            head=head->next;
        }
        return ispalin(str);
    }
