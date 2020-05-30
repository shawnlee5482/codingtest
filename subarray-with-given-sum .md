

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
    int start = 0;
    int end = 0;
    int sum = 0;
    
    while(start <= end && start < size && end < size ) {
        sum = sum + arr[end];
        if(sum > target) {
            sum = sum - arr[start] - arr[end];
            start++;
            if(start > end) {
                end=start;
                sum = 0;
            }
            continue;
        }
        if(sum == target) {
            cout << start+1 << " " << end+1 << endl;
            return;
        }
        end++;
    }
    cout << -1 << endl;
                
```
