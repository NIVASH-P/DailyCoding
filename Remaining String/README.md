Remaining String

Program:
    string printString(string s, char ch, int count) {
        // Your code goes here
        string ans = "";
        int c = 0;
        for(int i=0;i<s.length();i++)
        {
            if(s[i] == ch && c == count-1)
            {
                ans = s.substr(i+1,s.length());
                break;
            }
            else if(s[i] == ch)
            {
                c++;
            }
        }
        return ans;
    }
