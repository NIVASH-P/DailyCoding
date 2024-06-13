Question 1:
Given a number n, find the nth number in the Padovan Sequence.

A Padovan Sequence is a sequence which is represented by the following recurrence relation
P(n) = P(n-2) + P(n-3)
P(0) = P(1) = P(2) = 1

Note: Since the output may be too large, compute the answer modulo 10^9+7.


Solution:

  int padovanSequence(int n)
    {
       //code here
        int a = 1,b = 1,c=1;
        if(n <= 2)
            return 1;
        int sum = 0;
        for(int i=3;i<=n;i++)
        {
            sum = (a+b)%1000000007;
            a = b%1000000007;
            b = c%1000000007;
            c = sum%1000000007;
        }
        return sum;
    }
