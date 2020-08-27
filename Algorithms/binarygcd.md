---

layout: default-algo
title: Algorithms.
problem: Binarygcd

---

# Problem


* Binarygcd

# Implementation

~~~
cpp

#include<bits/stdc++.h>
using namespace std;

int gcd(int a, int b) {

	if (a == 0)
		return b;
	if (b == 0)
		return a;

	int powerOf2;
	for (powerOf2 = 0; ((a | b) & 1) == 0; powerOf2++) {
		a >>= 1;
		b >>= 1;
	}

	while ((a & 1) == 0)
		a >>= 1;

	while (b != 0) {
		while ((b & 1) == 0)
			b >>= 1;
		if (a > b)
			swap(a, b);
		b -= a;
	}
	return a << powerOf2;
}

int main() {
    int a,b;
    cin>>a>>b;
	cout << gcd(a,b) << endl;
	return 0;
}
~~~
