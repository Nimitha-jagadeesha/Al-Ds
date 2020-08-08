---

layout: default-algo
title: Algorithms.
problem: DFS(Depth first search)

---

# Problem


* DFS

# Implementation

~~~
cpp

#include<bits/stdc++.h>

using namespace std;

vector<int> adj[1000];            
bool visited[1000]={false} ;               
void dfs(int source)
{
    visited[source] = true;

    queue<int> q;
    q.push(source);

    while(!q.empty())
    {
        source = q.front() ;
        q.pop();

        for(int i=0; i<adj[source].size() ;i++)      
        {
            int neighbour = adj[source][i];
            if( !visited[neighbour])
               {
                visited[neighbour] = true;
                 q.push(neighbour);
               }
        }
    }

}

int main()
{
    int vertices,edges;
    cin>>vertices>>edges;

    for(int i=0; i<edges ; i++)
    {
        int u,v;
        cin>>u>>v;
        adj[u].push_back(v);
        adj[v].push_back(u);
    }

    int source;
    cin>>source;

    dfs(source);

    return 0;
}

~~~
* Time Complexity : **O(V+E)**  where **V** is the number of vertexes and **E** is the number of edges.
