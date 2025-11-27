# Ex.No:4

# Ex.Name: Write A C++ Program to represent the Adjacency Matrix


## Date:16/10/2025

## Aim:
To write a C++ program to represent a graph using an Adjacency Matrix.

## Algorithm:
```
1. Read the number of vertices `n`.
2. Create a 2D vector (or array) of size `n × n` initialized to 0.
3. Read the number of edges `e`.
4. For each edge (u, v):

   * Set `adj[u][v] = 1`.
   * For an undirected graph, also set `adj[v][u] = 1`.
5. Display the adjacency matrix.
```




## Program:
```cpp
#include<iostream>
using namespace std;
int vertArr[20][20]; 
int count = 0;
void displayMatrix(int v) 
{
    int i,j;
    for(i=0;i<v;i++)
    {
        for(j=0;j<v;j++)
        {
            cout<<vertArr[i][j]<<" ";
        }
        cout<<endl;
    }
}
void add_edge(int u, int v) 
{      
    vertArr[u][v] = 1;
    vertArr[v][u] = 1;
  
}
int main() 
{
    int x=6,a,b;
   for(int i=0;i<6;i++)
   {
       cin>>a>>b;
        add_edge(a,b);
   }
   displayMatrix(x);
   return 0;
   return 0;
}
```



## Output:
<img width="394" height="516" alt="image" src="https://github.com/user-attachments/assets/185c779f-c9e3-4194-a65e-77d721297a2b" />



 ## Result:
Thus, the graph was successfully represented using an Adjacency Matrix in C++.

