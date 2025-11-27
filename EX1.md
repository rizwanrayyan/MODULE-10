# Ex.No:1

# Ex.Name:Write A CPP Program to implement BFS using vectors and queue (use double data)

## Date: 16/10/2025
## Aim:
To write a C++ program to perform Breadth First Search (BFS) on a graph using vectors for adjacency representation and a queue, with nodes represented using double data type.

## Algorithm:
```
1. Read the number of vertices.
2. Create an adjacency list using a vector of vectors storing **double** values.
3. Insert edges into the adjacency list.
4. Maintain a `visited` vector initialized to `false`.
5. Use a queue to perform BFS:

   * Push the starting node into the queue and mark it visited.
   * While the queue is not empty:

     * Pop a node from the queue and print it.
     * For all adjacent nodes:

       * If not visited, mark visited and push into queue.
6. End after all reachable nodes are visited.
```

## Program:
```cpp
#include <bits/stdc++.h>
#define pb push_back

using namespace std;

vector<bool> v;
vector<vector<int> > g;

void edge(int a, int b)
{
    g[a].pb(b);
    g[b].pb(a);
}

void bfs(int u)
{
	queue<int> q;
	q.push(u);
	v[u]=true;
	
	while(!q.empty())
	{
	    int n = q.front();
	    q.pop();
	    cout<<n<<" ";
	    
	    for(auto i=g[n].begin();i!=g[n].end();i++)
	    {
	        if(!v[*i])
	        {
	            q.push(*i);
	            v[*i] = true;
	        }
	    }
	}
}

int main()
{
	int n,a;
    cin>>n>>a;
    
    v.assign(n,false);
    g.assign(n, vector<int> ());
    int x,y;
    for(int i=0;i<a;i++)
    {
        cin>>x>>y;
        edge(x,y);
    }
    for(int i=0;i<n;i++)
    {
        if(!v[i])
            bfs(i);
        
    }
	return 0;
}
```


## Output:
<img width="379" height="393" alt="image" src="https://github.com/user-attachments/assets/69553533-8a66-4072-8f09-8c1e82f5407f" />



 ## Result:
Thus, the BFS traversal was successfully implemented in C++ using vectors for graph representation and a queue, with node values stored as double datatype.

