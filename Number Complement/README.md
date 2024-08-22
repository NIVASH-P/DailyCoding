Number Complement:
  class Solution {
public:
    int findComplement(int num) {
        string bin = "";
        while(num != 0)
        {
            if(num%2 == 0)
            {
                bin+='1';
            }
            else
            {
                bin+='0';
            }
            num/=2;
        }
        int ans = 0;
        // reverse(bin.begin(),bin.end());
        cout<<bin<<endl;
        for(int i=0;i<bin.length();i++)
        {
            if(bin[i] == '1')
            {
                ans += pow(2,i);
            }
        }
        return ans;
    }
};
