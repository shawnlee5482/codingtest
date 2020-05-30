

https://practice.geeksforgeeks.org/problems/subarray-with-given-sum/0

```
#include <iostream>
#include <vector>

using namespace std;

void find(vector<int> arr, int size, int target);

int main() {
    int ncase;
    int target;
    int size;
    
    cin >> ncase;
    for(int i = 0; i < ncase; i++) {
        cin >> size;
        cin >> target;
        vector<int> arr;
        for(int j = 0; j < size; j++) {
            int num;
            cin >> num;
            arr.push_back(num);
        }
        find(arr, size, target);
    }
	return 0;
}

void find(vector<int> arr, int size, int target) {
    for(int i = 0; i < size; i++) {
        int sum = arr[i];
        if(arr[i] == target) {
            cout << i+1 << " " << i+1 << endl;
            return;
        }
        for(int j = i+1; j < size; j++) {
            sum += arr[j];
            if(sum == target) {
                cout << i+1 << " " << j+1 << endl;
                return;
            }
            if(sum >= target) break;
        }
    }
    cout << -1 << endl;
}
                
```
