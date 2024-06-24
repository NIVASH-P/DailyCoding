Summed Matrix

Algorithm:
 i) find absoulute difference for n and q
 ii) return absoulute difference-1


 Coding:
   long long sumMatrix(long long n, long long q) {
        // code here
        if(n*2 < q || q == 0)
            return 0;
        long long diff = abs((n+1)-q);
        return n-diff;
    }
