# longest-distinct-characters-in-string

** Try all substring
** using hash check duplication fast

```
#include <iostream>
#include<bits/stdc++.h>
using namespace std;

string s;

int max(int a, int b)
{
    return a > b ? a : b;
}

int main()
 {
	int t; cin >> t;
	while(t--) {
	    cin >> s;
	    // init res as 0
	    int res = 0;
	    // init hash size length of 256
	    int hash[256]; 
	    
	    int l = s.length();
        // iterate i from 0 to l-1
        for(int i = 0; i < l; i++) {
            // initiate count = 0
            int count = 1;
            // init hash and set s[i] in hash
            for(int i = 0; i < 256; i++) hash[i] = 0;
            hash[s[i]] = 1;
            // iterate j from i+1 to l-1
            for(int j = i+1; j < l; j++) {
                // if s[j] is in string(i~j-1) break;
                if(hash[s.at(j)]) break;
                hash[s[j]] = 1;
                // else increase count by 1
                count++;
            }
            res = max(count, res);
        }
        cout << res << endl;
	}
	    
	return 0;
}
```
