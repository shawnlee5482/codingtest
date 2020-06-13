# form-a-panlindrome

#include <iostream>
#include<bits/stdc++.h>
using namespace std;

// calc(start, end) return number of insert required to make s as palindrome

// if start >= end, return 0 (invalid or one character)
// if both end is same, return calc(start+1, end-1)
// if it is cached already return it
// if both end is different, take min between
// 1) start is duplicated, calc(start+1, end)
// 2) end is duplicated calc(start, end-1)
// store min(first, second) + 1
// and memoize it and return

string s;

int cache[40][40];

int calc(int start, int end) 
{
    if(start >= end) return 0;
    if(s[start] == s[end]) return calc(start+1, end-1);
    if(cache[start][end]) return cache[start][end];
    int res1 = calc(start+1, end);
    int res2 = calc(start, end-1);
    int res;
    if(res1 < res2) res = res1;
    else res = res2;
    res++;
    cache[start][end] = res;
    return res;
}

int main()
 {
	int t; cin >> t;
	getline(cin, s);
	while(t--) {
	    for(int i = 0; i < 40; i++) {
	        for(int j = 0; j < 40; j++) {
	            cache[i][j] = 0;
	        }
	    }
	    getline(cin, s);
	    cout << calc(0, s.length()-1) << endl;  // n is string length
	}

	return 0;
}
