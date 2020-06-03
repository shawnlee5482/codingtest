# codingtest

```
#include <iostream>

using namespace std;

int mina;

int calc(int a[], int n, int m, int count) {
  if(n <= 0 || a[n] == 0) return count;

  if(count > mina) return count;

  int nn;
  
  if(a[n] != -1) nn = a[n];
  else nn = n;

  if(nn == 0) return count;

  if(nn < m) {
    if(mina > count + 1) mina = count + 1;
    return count + 1;
  }

  for(int i = 1; i < m + 1; i++) {
    int res = calc(a, nn - i, m, count + 1);
    if(res < mina) {
      mina = res;
    }
  }

  return mina;
}

int main() {
  int m = 6;  // dice
  int v[] = {-1, -1, -1, -1, -1, -1, 
             -1, -1, -1, -1, -1, -1,
             -1, -1, -1, -1, -1, -1,
             -1, -1, -1, -1, -1, -1,
             -1, -1, -1, -1, -1, -1
            };
  // ladder (since we trace back from highest number to smalle
  v[21] = 2;
  v[25] = 10;
  v[7] = 4;
  v[28] = 19;
  
  // // snake (26 -> 1)
  v[1] = 26;

  // for display ladder and snake
  for(int i = 0; i < 5; i++) {
    for(int j = 0; j < 6; j++) {
      cout << v[i*6 + j] << " ";
    }
    cout << endl;
  }
  //int v[] = {-1, 0, -1, -1};
  int n = sizeof(v) / sizeof(v[0]) - 1;
  mina = n;

  int count = 0;
  cout << calc(v, n, m, count);
}
```
