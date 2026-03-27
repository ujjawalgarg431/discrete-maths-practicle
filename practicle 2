# Validating Graph using Adjacency Matrix

```python
def is_valid_graph(n, adj_matrix):
    # Check if matrix is square and binary (0/1)
    if len(adj_matrix) != n or any(len(row) != n for row in adj_matrix):
        return False
    for i in range(n):
        for j in range(n):
            if adj_matrix[i][j] not in [0, 1]:
                return False
    return True

n = int(input("Enter number of vertices: "))
adj_matrix = []
print("Enter adjacency matrix row-wise:")
for i in range(n):
    row = list(map(int, input().split()))
    adj_matrix.append(row)

if is_valid_graph(n, adj_matrix):
    print("Valid adjacency matrix representation of a graph.")
else:
    print("Invalid adjacency matrix!")
```

SAMPLE INPUT :-
```
Enter number of vertices: 3
Enter adjacency matrix row-wise:
0 1 1
1 0 1
1 1 0
```

OUTPUT :-
```
Valid adjacency matrix representation of a graph.
```


# Checking if Graph is Complete (Adjacency List)

```cpp
#include <bits/stdc++.h>
using namespace std;

bool isComplete(int n, vector<vector<int>>& adjList) {
    int edges = 0;
    for (int i = 0; i < n; i++) {
        if (adjList[i].size() != n - 1) return false;
        edges += adjList[i].size();
    }
    return edges == n * (n - 1) / 2; // No self-loops/duplicates assumed
}

int main() {
    int n, e;
    cout << "Enter vertices, edges: ";
    cin >> n >> e;
    vector<vector<int>> adjList(n);
    cout << "Enter " << e << " edges (u v):\n";
    for (int i = 0; i < e; i++) {
        int u, v;
        cin >> u >> v;
        adjList[u].push_back(v);
        adjList[v].push_back(u);
    }
    cout << (isComplete(n, adjList) ? "Complete graph" : "Not complete") << endl;
    return 0;
}
```

SAMPLE INPUT :-
```
Enter vertices, edges: 3 3
Enter 3 edges (u v):
0 1
0 2
1 2
```

OUTPUT :-
```
Complete graph
```

SAMPLE INPUT (2) :-
```
Enter vertices, edges: 3 2
Enter 2 edges (u v):
0 1
1 2
```

OUTPUT (2) :-
```
Not complete
```


# In-Degree and Out-Degree (Directed Graph, Adjacency Matrix)

```python
n = int(input("Enter number of vertices: "))
adj_matrix = []
print("Enter adjacency matrix row-wise:")
for i in range(n):
    row = list(map(int, input().split()))
    adj_matrix.append(row)

in_degree = [0] * n
out_degree = [0] * n

for i in range(n):
    for j in range(n):
        if adj_matrix[i][j] == 1:
            out_degree[i] += 1
            in_degree[j] += 1

print("Vertex | In-Degree | Out-Degree")
for i in range(n):
    print(f"{i:6} | {in_degree[i]:9} | {out_degree[i]:10}")
```

SAMPLE INPUT :-
```
Enter number of vertices: 3
Enter adjacency matrix row-wise:
0 1 0
0 0 1
1 0 0
```

OUTPUT :-
```
Vertex | In-Degree | Out-Degree
     0 |         1 |          1
     1 |         1 |          1
     2 |         1 |          1
```
