# codingtest

https://practice.geeksforgeeks.org/problems/count-the-triplets/0


```
#include <iostream>
#include <vector>
#include <algorithm>
#include <unordered_map>

using namespace std;

int main() {
    int ncase;
    int target;
    int size;
    
    cin >> ncase;
    for(int i = 0; i < ncase; i++) {
        cin >> size;
        vector<int> arr;
        for(int j = 0; j < size; j++) {
            int num;
            cin >> num;
            arr.push_back(num);
        }
        // make a cache
        sort(arr.begin(), arr.end()); 
        
        int count = 0;
        // Once it is sorted, from the largest value (end), find pair from 0 to end-1
        for(int end = size - 1; end >= 2; end--) {
            int s = 0, e = end-1;
            while(s < e) {
                int x = arr[s] + arr[e];
                // if sum is larger than target, it means we should decrese end since we should add the less value
                if(x > arr[end]) {
                    e--;
                } else if(x < arr[end]) {  // if sum is smaller, we should increase start since we should add more
                    s++;
                } else {
                    // if we find the target, increase count 
                    // and continue to find another matching pair 
                    count++;
                    s++;
                    e--;
                }
            }
        }
        if(count > 0) {
            cout << count << endl;
        } else {
            cout << -1 << endl;
        }
    }
	return 0;
}
```
