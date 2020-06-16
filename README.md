# Relative Sorting

```
#include <iostream>
#include <bits/stdc++.h>
using namespace std;

#define MAX 100000
int main()
 {
	int t; cin >> t;
	while(t--) {
	    int na; cin >> na;
	    int nb; cin >> nb;
	    int a[MAX], b[MAX];
	    
	    for(int i = 0; i < na; i++) cin >> a[i];
	    for(int i = 0; i < nb; i++) cin >> b[i];
	    
        int hash[MAX], hash2[MAX];
        vector<int> t;
        int lenb = sizeof(b) / sizeof(b[0]);
        int lena = sizeof(a) / sizeof(a[0]);
        for(int i = 0; i < MAX; i++) {
            hash[i] = 0;
            hash2[i] = 0;
        }
        for(int i = 0; i < nb; i++) {
            hash[b[i]] = 1;
        }
        for(int i = 0; i < na; i++) {
            if(hash[a[i]]) {
                hash2[a[i]]++;
            } else {
                t.push_back(a[i]);
            }
        }
        
      
        for(int i = 0; i < nb; i++) {
            for(int j = 0; j < hash2[b[i]];  j++) {
                cout << b[i] << " ";
            }
        }
    
        sort(t.begin(), t.end());
        for(vector<int>::iterator j=t.begin(); j != t.end(); j++) {
            cout << *j;
            if(j != t.end()) cout << " " ;
        }
        cout << endl;
	}
	return 0;
}
```
