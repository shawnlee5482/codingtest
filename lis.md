# Longest Increasing Sequence

```
#include <iostream>

int test[] = {3, 2, 6, 4, 5, 1};

using namespace std;

int main() {
  int n = sizeof(test) / sizeof(test[0]);
  int l[n];

  // fill array as 1
  fill(l, l+n, 1);

  int maxl = -1;
  for(int i = 1; i < n; i++) {
    // for previous indexes
    for(int j = 0; j < i; j++) {
      // find max l[j] with tail is less than current value
      if(l[j] + 1 > l[i] && test[i] > test[j]) {
        // update l[i]
        // always l[i] have the largest
        l[i] = l[j] + 1;
      }
    }
    // to get max l[i]
    if(maxl < l[i]) maxl = l[i];
  }
  cout << maxl;
}
```
