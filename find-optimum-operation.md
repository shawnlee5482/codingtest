# codingtest

```
#include <iostream>
#include<bits/stdc++.h>
using namespace std;

int calc(int n) {
    if(n <= 1) return n;

    if(n % 2 == 0) {
        return calc(n/2) + 1;
    } else {
        return calc(n-1) + 1;
    }
}

int main()
 {
	int t; cin >> t;
	while(t--) {
	    int n; cin >> n;
	    cout << calc(n) << endl;
	}
	    
	return 0;
}
```
