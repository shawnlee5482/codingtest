# codingtest

https://practice.geeksforgeeks.org/problems/reverse-words-in-a-given-string/0

```
#include<iostream>
#include <bits/stdc++.h>

using namespace std;
int main()
 {
	int t; cin >> t;
	while(t--) {
	  string s; cin >> s;
      int pos = s.size();
      int newpos = s.size() - 1;
      while(pos != -1 ) {
        newpos = s.find_last_of('.', pos-1);
        cout << s.substr(newpos+1, pos-newpos-1);
        if(newpos != -1) cout << ".";
        pos = newpos;
      }
	  cout << endl;
	}

	    
	return 0;
}
```
