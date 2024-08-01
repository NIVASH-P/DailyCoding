Number of Senior Citizens:
  Program:
    int countSeniors(vector<string>& details) {
        int ans = 0;
        int n = details.size();
        for(auto& detail : details)
        {
            string str = "";
            str+=detail[11];
            str+=detail[12];
            cout<<str<<endl;
            int num = stoi(str);
            if(num > 60)
            {
                ans++;
            }
        }
        return ans;
    }
