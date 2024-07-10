Crawler Log Folder
Algorithm
  i)Stack
Program:
  int minOperations(vector<string>& logs) {
        stack<string>st;
        bool f = 0;
        for(auto& i : logs)
        {
            if(i == "./")
            {
                continue;
            }
            if(i == "../")
            {
                if(!st.empty())
                {
                    st.pop();
                }
            }
            else
                st.push(i);
        }
        int ans = st.size();
        return ans;
    }
