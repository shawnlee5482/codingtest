# codingtest
# test122123
```
#include <iostream>
#include <vector>
#include <algorithm>
#include <climits>

using namespace std;

int main()
 {
	int t; cin >> t;
	while(t--) {
	    int n; cin >> n;

	    int v[n];
	    for(int i = 0; i < n; i++) cin >> v[i];

	    int m; cin >> m;
	    
	    if(m == 1) {
	        cout << 0 << endl;
	        continue;
	    }
	    
	    sort(v, v+n);
	    int min = v[n-1] - v[0];
        int d;
        
	    for(int i = 0; i < n - m + 1; i++) {
	        d = v[i+m-1] - v[i];
	        if(d < min) min = d;
	        if(min == 0) break;
	    }
	    cout << min << endl;
	}
	    
	return 0;
}

```
