#include<bits/stdc++.h>
using namespace std;
int count( int S[], int m, int n ) 
{ 
    int i, j, x, y;  
    int table[n + 1][m]; 
    for (i = 0; i < m; i++) 
    {
    	table[0][i]=1;
	}   
    for (i = 1; i < n + 1; i++) 
    { 
        for (j = 0; j < m; j++) 
        {
            if(i-S[j] >= 0)
			{
				x=table[i-S[j]][j];
			}
			else
			{
				x=0;
			} 
			if(j>=1)
			{
				y=table[i][j-1];
			} 
			else
			{
			 	y=0;
			}
            table[i][j] = x + y; 
        } 
    } 
    return table[n][m - 1]; 
} 
int main()
{
	//your code goes here
	int coins;
	cout << "total number of coins" << endl;
	cin >> coins;
	int a[coins];
	cout << "value of coins" << endl;
	for(int i=0;i<coins;i++)
	{
		cin >> a[i];
	}
	int total_cents;
	cout << "total cents" << endl;
	cin >> total_cents;
	cout << "total number of ways" << endl;
	cout << count(a,coins,total_cents) << endl;
	return 0;
}
