# codingtest


```
#include <iostream>
#include <vector>
#include <map>

using namespace std;

int main() {
	//create hash
	
	//iterate array
	    //put the count in hash, update major_num, max_count
	//if max_count > n / 2,  print majo_num otherwise -1
    int t; cin >> t;
    for(int i = 0; i < t; i++) {
        int n; cin >> n;
        
        map<int, int> h;
        vector<int> v(n);
        
        int k;
        int max = 0, max_count = 0;

        for(int j = 0; j < n; j++) {
            cin >> v[j];
            h[v[j]]++;
        }

        // major number should appear in the first half at least once
        for(int j = 0; j < n / 2; j++) {
            k = v[j];
            if(h[k] > max_count) {
                max_count = h[k];
                max = k;
            }
        }
        if(max_count > n/2) {
            cout << max << endl;
        } else {
            cout << -1 << endl;
        }
    }
	return 0;
}
```
