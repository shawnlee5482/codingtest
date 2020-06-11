# k-th-elment-of-two-sorted-array

```
#include<bits/stdc++.h>
using namespace std;

int main()
{
    int t;
    cin>>t;
    while(t--)
    {
        int n,m,k;
        cin>>n>>m;
        cin>>k;
        int a[n], b[m];
        int i, j;
        for(i=0;i<n;i++) {
            cin >>a[i];
        }
        for(i=0;i<m;i++) {
            cin >>b[i];
        }
        
        int res;
        i = 0; j = 0;
        while((i < n || j < m) && k > 0) {
            // take from a either
            // a[i] is less than b[j]
            // or b already pass the end
            if(j > m-1 || (a[i] < b[j] && i < n)) {
                res = a[i];
                i++;
                k--;
            } else {
                res = b[j];
                j++;
                k--;                
            }
        }
        cout<<res <<endl;
    } 

}


```
