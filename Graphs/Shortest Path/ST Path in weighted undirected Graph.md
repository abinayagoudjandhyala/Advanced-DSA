# Graph Practice – Shortest Path in Weighted Undirected Graph (Day Notes)

Today I worked on finding the **shortest path in a weighted undirected graph** using **Dijkstra’s Algorithm**.

---

## Shortest Path in Weighted Undirected Graph

### Core Idea

Use **Dijkstra’s Algorithm** to find the shortest distance from a source node to all other nodes.

Since edges have **different weights**, BFS cannot be used.  
We use a **min-heap (priority queue)** to always process the closest node first.

---

### Logic

* Build adjacency list with **(node, weight)**
* Initialize distance array with large values
* Set source distance = 0
* Use **priority queue (min-heap)**:
  * Always pick node with smallest distance
* For each neighbor:
  * If a shorter path is found → update distance
  * Push updated node into queue
* Replace unreachable nodes with `-1`

---

## 💻 Code

```java
class Solution {
    public int[] dijkstra(int n, int[][] edges, int src) {

        // Step 1: Build adjacency list
        List<List<Pair>> adj = new ArrayList<>();
        for(int i = 0; i < n; i++){
            adj.add(new ArrayList<>());
        }

        for(int[] e : edges){
            int u = e[0], v = e[1], wt = e[2];

            adj.get(u).add(new Pair(v, wt));
            adj.get(v).add(new Pair(u, wt)); // undirected
        }

        // Step 2: Distance array
        int[] dist = new int[n];
        Arrays.fill(dist, (int)1e9);
        dist[src] = 0;

        // Step 3: Min Heap (priority queue)
        PriorityQueue<Pair> pq = new PriorityQueue<>((a, b) -> a.dist - b.dist);
        pq.add(new Pair(src, 0));

        // Step 4: Dijkstra Algorithm
        while(!pq.isEmpty()){
            Pair cur = pq.poll();
            int node = cur.node;
            int d = cur.dist;

            for(Pair nei : adj.get(node)){
                int v = nei.node;
                int wt = nei.dist;

                if(d + wt < dist[v]){
                    dist[v] = d + wt;
                    pq.add(new Pair(v, dist[v]));
                }
            }
        }

        // Step 5: Mark unreachable nodes
        for(int i = 0; i < n; i++){
            if(dist[i] == 1e9) dist[i] = -1;
        }

        return dist;
    }

    // Pair class
    static class Pair {
        int node, dist;
        Pair(int n, int d){
            node = n;
            dist = d;
        }
    }
}
```
![WhatsApp Image 2026-03-28 at 10 31 28 PM](https://github.com/user-attachments/assets/ab2d86df-042f-4f45-8bd8-9b46f5400227)
