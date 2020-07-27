---

layout: default-algo
title: Algorithms.
problem: BFS(Breadth first search)

---

# Problem


* Breadth First Traversal (or Search) for a graph is similar to Breadth First Traversal of a tree . The only catch here is, unlike trees, graphs may contain cycles, so we may come to the same node again. To avoid processing a node more than once, we use a boolean visited array. For simplicity, it is assumed that all vertices are reachable from the starting vertex.


# Implementation

~~~
cpp


#include<bits/stdc++.h>
using namespace std;
int main()
{
     long long int n,m,u,v;
     cin>>n>>m;
     vector<int>visted(n+1,0);
     vector<vector<int>>a(n+1);
     for(int i=0;i<m;i++)
     {
         cin>>u>>v;
         a[u].push_back(v);
         a[v].push_back(u);
     }
     queue<int>q;
     a.push(1);
     visited[1]=1;
     cout<<"BFS of  a given graph is"<<endl;
     while(a.size())
     {
         u=a.front();
         a.pop();
        for(i=0;i<a[u].size();i++)
        {
            if(visited[a[u][i]]==0)
            {
                q.push(a[u][i]);
                visited[a[u][i]]=1;
            }
        }
        cout<<u<<" ";
     }
}
~~~

* Time Complexity : $O$ $(E)$ where E represents number of edges
