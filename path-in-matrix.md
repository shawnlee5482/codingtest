# Path in Matrix

https://practice.geeksforgeeks.org/problems/path-in-matrix/0

```
#include <iostream>
#include<bits/stdc++.h>
using namespace std;

int n;
int **v;
int **visited;

int count_path(int i, int j) {
    int res = v[i][j];
    int c;
    if(i == n - 1) return res;
    if(visited[i][j] != 0) return visited[i][j];
    
    if(i < n-1 && j < n-1) {
        c = count_path(i+1, j+1) + v[i][j];
        res = c > res ? c: res;
    }
    if(i < n-1) {
        c = count_path(i+1, j) + v[i][j];
        res = c > res ? c: res;
    }
    if(i < n-1 && j > 0) {
        c = count_path(i+1, j-1) + v[i][j];
        res = c > res ? c: res;
    }
    visited[i][j] = res;
    return res;
}

int main()
 {
	int t; cin >> t;
	while(t--) {
	    cin >> n;
	    // mem alloc
	    v = new int*[n];
	    for(int i = 0; i < n; i++) v[i] = new int[n];
	    visited = new int*[n];
	    for(int i = 0; i < n; i++) {
	        visited[i] = new int[n];
	    }
	    for(int i = 0; i < n; i++) {
	        for(int j = 0; j < n; j++) {
	            visited[i][j] = 0;
	        }
	    }
	    // read in data
	    for(int i = 0; i < n; i++) {
	        for(int j = 0; j < n; j++) {
	            cin >> v[i][j];
	        }
	    }
	    int max_length = 0;
	    for(int i = 0; i < n; i++) {
            int length = count_path(0, i);
            if(length > max_length) max_length = length;
	    }
	    cout << max_length << endl;
	    
	    // free
	    for(int i = 0; i < n; i++) delete v[i];
	    delete v;
	}
	    
	return 0;
}
```
