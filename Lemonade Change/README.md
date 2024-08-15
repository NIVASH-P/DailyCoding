Lemonade Change:

  Program:
    class Solution {
public:
    bool lemonadeChange(vector<int>& bills) {
        int curr = 0;
        int n = bills.size();
        map<int,int>mp;
        for(int i=0;i<n;i++)
        {
            cout<<mp[5]<<" "<<mp[10]<<" "<<mp[20]<<endl;
            if(bills[i] == 5)
            {
                mp[bills[i]]++;
            }
            if(bills[i] == 10)
            {
                if(mp[5] >= 1)
                {
                    mp[5]--;
                }
                else
                {
                    return false;
                }
                mp[bills[i]]++;
            }
            if(bills[i] == 20)
            {
                if((mp[5] >= 1 && mp[10] >= 1))
                {
                    mp[5]--;
                    mp[10]--;
                }
                else if(mp[5] >= 3)
                {
                    mp[5]-=3;
                }
                else
                {
                    return false;
                }
                mp[20]++;
            }
        }
        return true;
    }
};
