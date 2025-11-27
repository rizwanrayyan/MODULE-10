# Ex.No: 3

# Ex.Name: Write A C++ Program for Topological Sorting (using vector and algorithm STLs)

## Date: 16/10/2025

## Aim:
To write a C++ program to perform Topological Sorting on a Directed Acyclic Graph (DAG) using vector STL and algorithm STL.

## Algorithm:
```
1. Read the number of vertices.
2. Create an adjacency list using `vector<vector<int>>`.
3. Insert directed edges into the graph.
4. Maintain a `visited` vector initialized to `false`.
5. Maintain a stack or vector to store the topological order.
6. Use recursive DFS:

   * Mark the current node visited.
   * Recursively call DFS on all unvisited neighbors.
   * After finishing all neighbors, push the node into the result vector.
7. After processing all nodes, **reverse** the result vector using `reverse()` from `<algorithm>`.
8. Display the topological order.
```




## Program:
```cpp
#include <iostream>
#include <vector>
#include <algorithm>

struct pair 
{
	int a, b;
	pair(int a, int b) : a(a), b(b) {}
	
	std::ostream &print(std::ostream &out) const 
	{
		return (out << "(" << a << ", " << b << ")");
	}
};

std::ostream &operator<<(std::ostream &out, const pair &p) 
{ 
    return p.print(out); 
    
}

struct topological_pair_comparator 
{
	bool operator()(const pair &p, const pair &q) const 
	{ 
	    return p.a<q.a && p.b<q.b; 
	    
	}
} tpc;

std::vector<pair> pairs = 
{
     pair(1,1),
    pair(1,2),
	pair(2,1),
	pair(3,1),
	pair(1,3),
	pair(5,5),
	pair(2,2),
	pair(4,0)

//write code here
};

int main() {
	std::sort(pairs.begin(), pairs.end(), tpc);
	for(const pair &p : pairs) std::cout << p << " ";
	std::cout << std::endl;
	return 0;
}
```



## Output:
<img width="832" height="111" alt="image" src="https://github.com/user-attachments/assets/99291751-07ba-4342-a02a-4cc07f4dbab1" />



 ## Result:
Thus, the topological sorting of a directed graph was successfully implemented in C++ using vector and algorithm STL.

