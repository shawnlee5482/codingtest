# codingtest

Assuming array is not in sort
sum = n * (n + 1) / 2

```
#include <iostream>
#include <vector>

using namespace std;

int main() {
    int t; cin >> t;
    for(int i = 0; i < t; i++) {
        int n; cin >> n;
        vector<int> v(n);
        int sum = 0, k;
        for(int j = 0; j < n - 1; j++) {
            cin >> k;
            sum += k;    
        }
        cout << (n * (n+1) / 2 - sum) << endl;
    }
	//code
	return 0;
}
```
