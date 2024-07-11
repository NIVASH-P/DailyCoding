Reverse Substrings Between Each Pair of Parentheses

Algorithm:
  i)Stack

Program:

  string reverseParentheses(string s) {
        stack<char>st;
        string str = "";
        for(int i=0;i<s.length();i++)
        {
            // cout<<str<<endl;
            if(s[i] == ')')
            {
                string temp = "";
                while(st.top() != '(')
                {
                    temp+=st.top();
                    st.pop();
                }
                // reverse(temp.begin(),temp.end());
                st.pop();
                cout<<temp<<endl;
                for(int j=0;j<temp.length();j++)
                {
                    st.push(temp[j]);
                }
            }
            else
            {
                st.push(s[i]);
            }
        }
        string ans = "";
        while(!st.empty())
        {
            ans+=st.top();
            st.pop();
        }
        reverse(ans.begin(),ans.end());
        return ans;
    }
