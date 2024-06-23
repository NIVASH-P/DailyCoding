Implement Balancing Paranthersis Concept:

vector<int> bracketNumbers(string str) {
        // Your code goes here
        vector<int>ans;
        stack<int>st;
        int c = 1;
        for(int i=0;i<str.length();i++)
        {
            if(str[i] == '(')
            {
                st.push(c);
                ans.push_back(c);
                c++;
            }
            if(str[i] == ')')
            {
                ans.push_back(st.top()); 
                st.pop();
            }
        }
        return ans;
    }
