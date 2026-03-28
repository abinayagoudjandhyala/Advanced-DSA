# Graph Practice – Eventual Safe States (Day Notes)

Today I solved a problem involving **cycle detection in directed graphs** using **reverse graph + topological sort (Kahn’s Algorithm)**.

---

## Eventual Safe States (LeetCode 802)

### Core Idea

A node is **safe** if all paths starting from it eventually lead to a **terminal node** (node with no outgoing edges).

Instead of detecting cycles directly, we **remove unsafe nodes** using topological sorting.

---

### Logic

* Reverse the graph:
  * If `u → v`, store `v → u`
* Compute indegree:
  * Number of outgoing edges in original graph
* Add all nodes with **indegree = 0** (terminal nodes) to queue
* Perform BFS:
  * Remove node from queue → mark as safe
  * Reduce indegree of its neighbors
  * If neighbor becomes 0 → add to queue
* Sort the result before returning

---

## 💻 Code

```java
class Solution {
    public List<Integer> eventualSafeNodes(int[][] graph) {
        int n = graph.length;

        int[] indegree = new int[n];
        List<List<Integer>> adj = new ArrayList<>();

        // Initialize adjacency list
        for(int i = 0; i < n; i++){
            adj.add(new ArrayList<>());
        }

        // Reverse graph + indegree calculation
        for(int i = 0; i < n; i++){
            for(int j : graph[i]){
                adj.get(j).add(i); // reverse edge
                indegree[i]++;
            }
        }

        // Queue for BFS
        Queue<Integer> q = new LinkedList<>();
        for(int i = 0; i < n; i++){
            if(indegree[i] == 0){
                q.add(i);
            }
        }

        List<Integer> ans = new ArrayList<>();

        // BFS (Topological Sort)
        while(!q.isEmpty()){
            int node = q.poll();
            ans.add(node);

            for(int nei : adj.get(node)){
                indegree[nei]--;
                if(indegree[nei] == 0){
                    q.add(nei);
                }
            }
        }

        Collections.sort(ans);
        return ans;
    }
}
```
![WhatsApp Image 2026-03-28 at 10 44 34 PM](https://github.com/user-attachments/assets/80e8bddb-d3c5-4cbc-8e16-8f22e2c01c1e)
