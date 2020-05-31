# codingtest


```
#include <iostream>
#include <vector>
#include <map>

using namespace std;

int main() {
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
            if(h[v[j]] > max_count) {
                max_count = h[v[j]];
                max = v[j];
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
