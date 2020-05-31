# Kadane alogorithm


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

# Using recursion
https://www.youtube.com/watch?v=ohHWQf1HDfU

```
#include <iostream>
#include <vector>
#include <algorithm>
#include <bits/stdc++.h> 
using namespace std;

int max(int a, int b) { return a > b ? a : b; }
int submax(vector<int> v, int left, int right);

int submax(vector<int> v, int left, int right) {
    // base condition
    if(left == right) return v[left];
    if(left < 0 || left > right || right >= v.size()) {
        //cout << "**" << left << " " << right << " ";
        return INT_MIN;
    }
	int mid = (left + right) / 2;
	int res = max(submax(v, 0, mid-1), submax(v, mid+1, right));
	
	int wholesum;
	int right_sum = v[mid+1];
	int max_value = v[mid+1];
	for(int i = mid + 2; i < right; i++) {
	    right_sum = right_sum + v[i];
	    max_value = max(right_sum, max_value);
	}
	wholesum = max_value;
	int left_sum = v[mid-1];
	max_value = v[mid-1];
	for(int i = mid - 2; i >= 0; i--) {
	    left_sum = left_sum + v[i];
	    max_value = max(left_sum, max_value);
	}
	wholesum += max_value;
	wholesum += v[mid];
	
    return max(res, wholesum);
}

int main() {
	int t; cin >> t;
	while(t--) {
	    int n; cin >> n;
	    vector<int> v(n);
	    for(int i = 0; i < n; i++) cin >> v[i];
	    cout << submax(v, 0, n-1) << endl;
	}
	return 0;
}
```
