#include <bits/stdc++.h>
using namespace std;

int main() {
    int n = 7;
    int arr[n]={-1, 0, 0, 1, 1, 3, 5};
    int ans = 0;
    for(int i=0;i<n;i++)
    {
        int count = 1;
        int value = arr[i];
        while(value != -1)
        {
            count++;
            value = arr[value];
        }
        ans = max(ans,count);
    }
    cout<<ans;
    return 0;
}
