// C++ program to acquire all n coins 
#include<bits/stdc++.h> 
using namespace std; 

// function to calculate min cost 
int minCost(int coin[], int n, int k) 
{ 
	// sort the coins value 
	sort(coin, coin + n); 

	// calculate no. of 
	// coins needed 
	int coins_needed = ceil(1.0 * n / 
							(k + 1)); 

	// calculate sum of 
	// all selected coins 
	int ans = 0; 
	for (int i = 0; i <= coins_needed - 1; 
									i++) 
		ans += coin[i]; 
	
	return ans; 
} 

// Driver Code 
int main() 
{ 
	int coin[] = {8, 5, 3, 10, 
				2, 1, 15, 25}; 
	int n = sizeof(coin) / sizeof(coin[0]); 
	int k = 3; 
	cout << minCost(coin, n, k); 
	return 0; 
} 
