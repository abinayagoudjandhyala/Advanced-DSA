# Graph Practice – Shortest Path in Directed Acyclic Graph (Day Notes)

Today I worked on finding the **shortest path in a Directed Acyclic Graph (DAG)** using **Topological Sort + Relaxation**.

---

## Shortest Path in DAG

### Core Idea

Use **Topological Sort** to process nodes in a valid order, then relax edges to compute shortest distances.

Since the graph has **no cycles**, we can safely process nodes in order.

---

### Logic

* Build adjacency list with **(node, weight)**
* Perform **Topological Sort (DFS)**
* Initialize distance array
* Process nodes in topological order:
  * For each neighbor:
    * If a shorter path is found → update distance
* Replace unreachable nodes with `-1`

---

## 💻 Code

```java
class Solution {

    public int[] shortestPath(int n, int m, int[][] edges) {

        // Step 1: Build adjacency list
        List<List<Pair>> adj = new ArrayList<>();
        for(int i = 0; i < n; i++){
            adj.add(new ArrayList<>());
        }

        for(int i = 0; i < m; i++){
            int u = edges[i][0];
            int v = edges[i][1];
            int wt = edges[i][2];

            adj.get(u).add(new Pair(v, wt));
        }

        // Step 2: Topological Sort (DFS)
        boolean[] vis = new boolean[n];
        Stack<Integer> st = new Stack<>();

        for(int i = 0; i < n; i++){
            if(!vis[i]){
                topo(i, adj, vis, st);
            }
        }

        // Step 3: Distance array
        int[] dist = new int[n];
        Arrays.fill(dist, (int)1e9);
        dist[0] = 0; // source node

        // Step 4: Process nodes in topo order
        while(!st.isEmpty()){
            int node = st.pop();

            if(dist[node] != 1e9){
                for(Pair p : adj.get(node)){
                    int v = p.node;
                    int wt = p.weight;

                    if(dist[node] + wt < dist[v]){
                        dist[v] = dist[node] + wt;
                    }
                }
            }
        }

        // Step 5: Mark unreachable nodes
        for(int i = 0; i < n; i++){
            if(dist[i] == 1e9) dist[i] = -1;
        }

        return dist;
    }

    // DFS for Topological Sort
    private void topo(int node, List<List<Pair>> adj, boolean[] vis, Stack<Integer> st){
        vis[node] = true;

        for(Pair p : adj.get(node)){
            if(!vis[p.node]){
                topo(p.node, adj, vis, st);
            }
        }

        st.push(node);
    }

    // Pair class
    static class Pair {
        int node, weight;
        Pair(int n, int w){
            node = n;
            weight = w;
        }
    }
}
```
<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/9c4dea6b-f9cd-408f-9631-1e01c1456a37" />

