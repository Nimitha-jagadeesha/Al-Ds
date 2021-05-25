---

layout: default-algo
title: Algorithms.
problem: Quick Sort

---

# Problem


* Sort the elements in an array 


# Implementation

~~~
cpp


#include <bits/stdc++.h>
using namespace std;
int part(int i, int a[],int n)
{
    int pivot = n,j=i-1;
    for(int w=i;w<n;w++)
    {
        if(a[w]<=a[pivot])
        {
            swap(a[w],a[++j]);
        }
    }
    swap(a[n],a[++j]);
    return j;
}
void quicksort(int i,int a[],int n)
{
    if(i<=n)
    {
        int p = part(i,a,n);
        quicksort(i,a,p-1);
        quicksort(p+1,a,n);
    }
}

int main()
{
    long long int n,i,j,k;
    cin>>n;
    int a[n];
    for(i=0;i<n;i++)
    {
        cin>>a[i];
    }
    quicksort(0,a,n-1);
    for(i=0;i<n;i++)
    {
        cout<<a[i]<<" ";
    }
}
~~~
