# Graph Practice – Shortest Path in Undirected Graph (Day Notes)

Today I solved the problem of finding the **shortest path in an unweighted undirected graph** using BFS.

---

## Shortest Path in Undirected Graph

### Core Idea

Use **BFS (Breadth First Search)** to find the shortest distance from a source node to all other nodes.

Since all edges have equal weight (1), BFS guarantees the shortest path.

---

### Logic

* Convert edges into an **adjacency list**
* Initialize a **distance array** with large values
* Set source distance = 0
* Use a **queue for BFS**
* Traverse graph level by level:
  * For each neighbor:
    * If a shorter path is found → update distance
    * Push neighbor into queue
* Replace unreachable nodes with `-1`

---

## 💻 Code

```java
class Solution {
    public int[] shortestPath(int[][] edges, int n, int m, int src) {

        // Step 1: Build adjacency list
        List<List<Integer>> adj = new ArrayList<>();
        for(int i = 0; i < n; i++){
            adj.add(new ArrayList<>());
        }

        for(int i = 0; i < m; i++){
            int u = edges[i][0];
            int v = edges[i][1];

            adj.get(u).add(v);
            adj.get(v).add(u); // undirected
        }

        // Step 2: Distance array
        int[] dist = new int[n];
        Arrays.fill(dist, (int)1e9);
        dist[src] = 0;

        // Step 3: BFS queue
        Queue<Integer> q = new LinkedList<>();
        q.add(src);

        // Step 4: BFS traversal
        while(!q.isEmpty()){
            int node = q.poll();

            for(int neighbor : adj.get(node)){
                if(dist[node] + 1 < dist[neighbor]){
                    dist[neighbor] = dist[node] + 1;
                    q.add(neighbor);
                }
            }
        }

        // Step 5: Mark unreachable nodes
        for(int i = 0; i < n; i++){
            if(dist[i] == 1e9) dist[i] = -1;
        }

        return dist;
    }
}
```
![WhatsApp Image 2026-03-28 at 10 24 00 PM](https://github.com/user-attachments/assets/b1ff3324-896b-431b-8061-174660273508)
<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/63447c36-c049-4791-a7c3-8ee1a1a9c4e9" />
<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/d9b3c60b-280d-44dc-80d6-cfdc07596c11" />
![WhatsApp Image 2026-03-28 at 10 25 46 PM](https://github.com/user-attachments/assets/477d7d42-6af6-4ea2-aa94-81c04eaca57a)

