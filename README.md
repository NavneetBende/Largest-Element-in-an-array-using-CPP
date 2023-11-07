# Largest-Element-in-an-array-using-CPP

Largest Element in an array in C++
Today we will learn Largest Element in an array in C++. In this program we will find the maximum element of the array using iterative approach. We will initialize the starting element of array as largest one and compare with all other elements of the given array and update the largest value.

 

Largest Element in an array in C++
While loop in C
Here, we will discuss three different  methods to find the maximum element among the given elements of the array. Method discussed in this page are given below,

Method 1: Simple iterative solution
Method 2: Top-Down recursive approach
Method 3: Bottom-Up recursive approach
Method 1 :-
Take a variable say max_element and assign it with value INT_MIN.
Run a loop form [0, N-1] and check,
If(arr[i]>max_element) then, set max_element = arr[i]
At last print the value of max_element.
Largest number in an array in C++
Method 1 : Code in C++
Run
#include<bits/stdc++.h>
using namespace std;

int main(){

  int arr[]={10, 89, 67, 56, 45, 78};
  int n = sizeof(arr)/sizeof(arr[0]);
  int max_element = INT_MIN;

  for(int i=0; i<n; i++){ if(arr[i]>max_element)
      max_element = arr[i];
  }

  cout<<max_element;
}
Output :
89
Related Pages
Given a set of positive integers, find all its subsets
 
Given a string s, remove all its adjacent duplicate characters recursively
 
Find Smallest Element in an Array

Find the Smallest and largest element in an array

Find Second Smallest Element in an Array

Method 2 (Using Recursion):
Create a recursive function say getmax(int arr[], int n)
Base condition : If(n==1) return arr[0]
Otherwise return max(arr[n-1], getmax( arr, n-1))
Method 2 : Code in C++
Run
#include<bits/stdc++.h>
using namespace std;

//Recursive Function
int getmax(int arr[], int n){
   if(n==1) return arr[0];

   return max(arr[n-1], getmax(arr, n-1));
}
//Driver Code
int main(){

   int arr[]={10, 89, 67, 56, 45, 78};
   int n = sizeof(arr)/sizeof(arr[0]);

   cout<<getmax(arr, n);
}
Output :
89
Method 3 (Using Recursion)
Call a function : maximum(int arr[], int i, int end)

With initial call up values as maximum(arr, 0, end)
Initially passing end as the index of last array element
Initially passing ‘i’ as 0
Recursively reach iteration where reading 2nd last element
Find larger between 2nd last and last array elements
And return the result to max value of the previous recursive iteration
In each of the remaining recursive callups find the largest b/w current array index element and current max value
Pass final max value from last recursive callup to main and print
Method 3 : Code in C++
Run
#include<bits/stdc++.h>
using namespace std;

//Recursive Function
int maximum(int arr[], int i, int end)
{
   int max;

   if(i == end-1)
     return (arr[i] > arr[i + 1]) ? arr[i] : arr[i + 1];

   max = maximum(arr, i + 1, end);

   return (arr[i] > max) ? arr[i] : max;
}
//Driver Code
int main(){

   int arr[]={10, 89, 67, 56, 45, 78};
   int n = sizeof(arr)/sizeof(arr[0]);

   cout<<maximum(arr, 0, n-1);
}
Output :
89
