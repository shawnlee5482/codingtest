# flood fill algorithm

```
#include <iostream>
#include<bits/stdc++.h>
using namespace std;

int row, col;
void flood_fill(int **m, int x, int y, int r, int c) {
    if(x < 0 || x >= row) return;
    if(y < 0 || y >= col) return;
    if(m[x][y] == c) return;
    
    if(m[x][y] == r) {
        m[x][y] = c;
        flood_fill(m, x+1, y, r, c);
        flood_fill(m, x-1, y, r, c);
        flood_fill(m, x, y+1, r, c);
        flood_fill(m, x, y-1, r, c);
    }
}

void print_array(int **m) {
    for(int i = 0; i < row; i++) {
        for(int j = 0; j < col; j++) {
            cout << m[i][j] << " ";
        }
    }
}

int main()
 {
	int t; cin >> t;
	while(t--) {
	    cin >> row; cin >> col;
	    int **m;
	    
	    m = new int *[row];
	    
	    for(int i = 0; i < row; i++) {
	        m[i] = new int[col];    
	    }

	    for(int i = 0; i < row; i++) {
	        for(int j = 0; j < col; j++) {
	            cin >> m[i][j];
	        }
	    }

	    int x; cin >> x; int y; cin >> y; int c; cin >> c;
	    flood_fill(m, x, y, m[x][y], c);
	    // print result
	    print_array(m);
	    cout << endl;

	}
	return 0;
}
```
