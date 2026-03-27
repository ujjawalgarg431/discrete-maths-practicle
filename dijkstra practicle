# Dijkstra Algorithm

Dijkstra’s Algorithm is a famous search algorithm used to find the shortest path between a starting node and every other node in a weighted graph.

Think of it as the mathematical engine behind Google Maps or flight route planners. If you want to get from City A to City E using the least amount of fuel or time, Dijkstra’s is the tool that calculates that route.

```python
import heapq

def dijkstra(graph, start):
    # Initialize distances with infinity and the start node with 0
    distances = {node: float('inf') for node in graph}
    distances[start] = 0
    
    # Priority queue: (distance, node)
    priority_queue = [(0, start)]
    
    while priority_queue:
        current_distance, current_node = heapq.heappop(priority_queue)
        
        # If we found a longer path than we already recorded, skip it
        if current_distance > distances[current_node]:
            continue
            
        # Check neighbors
        for neighbor, weight in graph[current_node].items():
            distance = current_distance + weight
            
            # If a shorter path is found, update and push to queue
            if distance < distances[neighbor]:
                distances[neighbor] = distance
                heapq.heappush(priority_queue, (distance, neighbor))
                
    return distances

# --- Sample Input and Execution ---
example_graph = {
    'A': {'B': 4, 'C': 2},
    'B': {'C': 5, 'D': 10},
    'C': {'B': 1, 'D': 3, 'E': 7},
    'D': {'E': 1},
    'E': {}
}

start_node = 'A'
results = dijkstra(example_graph, start_node)

print(f"Shortest distances from node {start_node}:")
for node, dist in results.items():
    print(f"To {node}: {dist}")
```

OUTPUT :-
```
Shortest distances from node A:
To A: 0
To B: 3
To C: 2
To D: 5
To E: 6
```

EXPLANATION :-
```python
distances = {node: float('inf') for node in graph}
distances[start] = 0
priority_queue = [(0, start)]
```
The Map (distances): We start by assuming every node is infinitely far away (float('inf')), except for our starting point, which is 0 distance from itself.

The To-Do List (priority_queue): This tracks which nodes we need to visit next. We use a min-heap because it automatically keeps the node with the smallest distance at the very top.
```python
while priority_queue:
    current_distance, current_node = heapq.heappop(priority_queue)
```
We keep going as long as there are nodes left to explore.

heappop grabs the node that is currently the "cheapest" to get to. This is the Greedy part of the algorithm—it always picks the immediate best option.
```python
if current_distance > distances[current_node]:
    continue
```
Because we might add the same node to our queue multiple times (if we find different paths to it), this line acts as a filter. If we’ve already found a better way to reach current_node than the one we just pulled from the queue, we ignore the old, longer path.
```python
for neighbor, weight in graph[current_node].items():
    distance = current_distance + weight
    
    if distance < distances[neighbor]:
        distances[neighbor] = distance
        heapq.heappush(priority_queue, (distance, neighbor))
```
Edge Relaxation: This is the heart of the code. We look at every neighbor connected to our current node.

The Math: We calculate: Current Distance to Node + Weight of the Edge to Neighbor.

The Decision: If this new path is shorter than the best one we previously recorded for that neighbor, we update our record and add that neighbor to the priority_queue to explore its own neighbors later.
How it works (The "Hospital Triage" Analogy)
Think of a hospital emergency room:

A regular list (list.append): Patients are seen in the order they walk in. If someone arrives with a broken arm first, and someone arrives with a heart attack second, the broken arm is treated first. This is inefficient for emergencies.

A Heap (heapq): Every time a new patient arrives, the computer instantly re-sorts the list so the person with the lowest survival time (the "smallest" number/highest priority) is moved to the front of the line.
