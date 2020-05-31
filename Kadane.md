# codingtest


https://practice.geeksforgeeks.org/problems/kadanes-algorithm/0


```
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

int main() {
	int t; cin >> t;
	while(t--) {
	    int n; cin >> n;
	    vector<int> v(n);
	    for(int i = 0; i < n; i++) cin >> v[i];
	    
      // set local sum and global sum as the first element
	    int lsum=v[0], gsum=v[0];
	    for(int i = 1; i < n; i++) {
          // compare local sum and a new item (keey previous some or restart)
	        lsum = max(v[i], lsum + v[i]);
          
          // even though we keep the previous some or restart, we have many cases, compare them and take max from them
	        gsum = max(lsum, gsum);
	    }
	    cout << gsum << endl;
	}
	return 0;
}

```
