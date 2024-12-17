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













// Online C++ compiler to run C++ program online
#include <bits/stdc++.h>
using namespace std;
void depth(int par[],int i,int* dep)
{
    if(dep[i])
    {
        return ;
    }
    if(par[i] == -1)
    {
        dep[i] = 1;
        return ;
    }
    if(dep[par[i]] == 0)
    {
        depth(par,par[i],dep);
    }
    dep[i] = dep[par[i]]+1;
}
int main() {
    int n = 7;
    int arr[n]={-1, 0, 0, 1, 1, 3, 5};
    int dep[n];
    for(int i=0;i<n;i++)
    {
        dep[i] = 0;
    }
    for(int i=0;i<n;i++)
    {
        depth(arr,i,dep);
    }
    int ans = 0;
    for(int i=0;i<n;i++)
    {
        if(ans < dep[i])
        {
            ans = dep[i];
        }
    }
    cout<<ans;

    return 0;
}
