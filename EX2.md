# Ex.No:2

# Ex.Name: Write A C++ Program to implementation DFS using Vector STL 

## Date:16/10/2025

## Aim:
To write a C++ program to perform Depth First Search (DFS) on a graph using vector STL for graph representation.

## Algorithm:
```
1. Read the number of vertices.
2. Create an adjacency list using `vector<vector<int>>`.
3. Insert edges into the adjacency list.
4. Maintain a `visited` vector initialized to `false`.
5. Create a recursive DFS function:

   * Mark the current node as visited and print it.
   * For each adjacent node:

     * If not visited, recursively call DFS.
6. Call DFS starting from a given starting node.
```




## Program:
```cpp
#include<bits/stdc++.h>
#define pb push_back
using namespace std;
vector<bool>v;
vector<vector<int>>g;
void edge(int a,int b)
{
    g[a].pb(b);
}
void bfs(int u)
{
    queue<int>q;
    q.push(u);
    v[u]=true;
    while(!q.empty())
    {
        int f=q.front();
        q.pop();
        cout<<f<<" ";
        for(auto i=g[f].begin();i!=g[f].end();i++)
        {
            if(!v[*i])
            {
                q.push(*i);
                v[*i]=true;
            }
        }
    }
}
int main()
{
    int n,e;
    cin>>n>>e;
    v.assign(n,false);
    g.assign(n,vector<int>());
    int a,b;
    for(int i=0;i<n;i++)
    {
        cin>>a>>b;
        edge(a,b);
    }
    for(int i=0;i<n;i++)
    {
        if(!v[i])
        {
            bfs(i);
        }
    }
    return 0;
}
```



## Output:
<img width="543" height="498" alt="image" src="https://github.com/user-attachments/assets/5a739367-2d6e-462c-a3a7-fdf3b9c19f8d" />



 ## Result:
Thus, DFS traversal was successfully implemented in C++ using vector STL for adjacency list representation.

