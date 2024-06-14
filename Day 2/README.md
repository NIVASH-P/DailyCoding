You are given a 3-digit number n, Find whether it is an Armstrong number or not.

An Armstrong number of three digits is a number such that the sum of the cubes of its digits is equal to the number itself. 371 is an Armstrong number since 33 + 73 + 13 = 371.

Note: Return "Yes" if it is an Armstrong number else return "No".


SOLUTION:

class Solution {
  public:
    string armstrongNumber(int n){
        // code here
        int m = n;
        int ans = 0;
        while(m != 0)
        {
            int a = m%10;
            ans+=(a*a*a);
            m/=10;
        }
        if(ans == n)
        {
            return "Yes";
        }
        return "No";
    }
};
