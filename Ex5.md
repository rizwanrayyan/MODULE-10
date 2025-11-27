# Ex.No:5

# Ex.Name: Write A C++ Graph implementation using STL for competitive programming | (DFS of Unweighted and Undirected)

## Date: 16/10/2025
## Aim:
To write a C++ program using STL to represent an unweighted, undirected graph and perform DFS traversal, optimized for competitive programming.

## Algorithm:
```
1. Read number of vertices `n` and edges `e`.
2. Create an adjacency list using `vector<vector<int>>`.
3. Insert each undirected edge in both directions.
4. Maintain a `visited` vector initialized to `false`.
5. Implement DFS:

   * Mark node as visited and print it.
   * For every neighbor in adjacency list:

     * If not visited, recursively call DFS.
6. Call DFS from a given start node.
```
## Program:
```cpp
#include <bits/stdc++.h>
using namespace std;
void addEdge(vector<int> adj[], int u, int v)
{
    adj[u].push_back(v);
}

void DFS(vector<int> adj[], int v, vector<bool> &vis)
{
    vis[v] = true;
    cout<<v<<" ";
    for(auto i :adj[v])
    {
        if(vis[i] == false)
        {
            DFS(adj, i , vis);
        }
    }
}

int main()
{ 
    int n ,a,b;
    cin>>n;
    vector<int>adj[n];
    vector<bool>visited(n,false);
    for(int i = 0 ;i < n ;i++)
    {
        cin>>a>>b;
        addEdge(adj,a,b);
    }
    DFS(adj, 1, visited);
}
```



## Output:
<img width="389" height="496" alt="image" src="https://github.com/user-attachments/assets/bdccea96-5c5a-4da4-b814-b351c360803d" />



 ## Result:
Thus, the DFS traversal of an unweighted, undirected graph was successfully implemented using vector STL, suitable for competitive programming.

