---

layout: default-algo
title: Algorithms.
problem: Binary Exponention

---

# Problem


* Find the a^n in just O(log(n)) multiplication.


# Implementation

~~~
cpp


#include<bits/stdc++.h>
using namespace std;


long long binpow(long long a, long long b) {
    long long res = 1;
    while (b > 0) {
        if (b & 1)
            res = res * a;
        a = a * a;
        b >>= 1;
    }
    return res;
}
int main()
{
     long long int a,n;
     cin>>a>>n;
     cout<<binpow(a,n);
}

~~~
* Time Complexity : **O(log(n))**
