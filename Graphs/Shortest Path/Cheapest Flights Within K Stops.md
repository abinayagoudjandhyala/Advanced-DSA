
# Graph Practice – Cheapest Flights Within K Stops (Day Notes)

Today I solved a problem involving **shortest path with constraints** using a combination of **BFS and cost optimization**.

---

## Cheapest Flights Within K Stops

### Core Idea

Find the **minimum cost** to reach a destination with at most **k stops**.

Use **BFS with cost tracking** instead of pure Dijkstra because of the stop constraint.

---

### Logic

* Build a directed graph using adjacency list
* Use a queue to perform BFS
* Each state stores:
  * current node
  * total cost so far
  * number of stops used
* Traverse neighbors:
  * If stops ≤ k and cost improves → update
  * Push new state into queue
* Track minimum cost for each node
* Return result if destination is reachable

---

## 💻 Code

```java
import java.util.*;

class Solution {
    class Pair {
        int dest, price;
        Pair(int d, int p) { dest = d; price = p; }
    }

    class State {
        int node, cost, stops;
        State(int n, int c, int s) { node = n; cost = c; stops = s; }
    }

    public int findCheapestPrice(int n, int[][] flights, int src, int dst, int k) {
        List<List<Pair>> graph = new ArrayList<>();
        for (int i = 0; i < n; i++) graph.add(new ArrayList<>());
        for (int[] f : flights) graph.get(f[0]).add(new Pair(f[1], f[2]));

        int[] minCost = new int[n];
        Arrays.fill(minCost, Integer.MAX_VALUE);
        minCost[src] = 0;

        Queue<State> q = new LinkedList<>();
        q.offer(new State(src, 0, 0));

        while (!q.isEmpty()) {
            State cur = q.poll();
            if (cur.stops > k) continue;

            for (Pair next : graph.get(cur.node)) {
                int newCost = cur.cost + next.price;

                if (newCost < minCost[next.dest]) {
                    minCost[next.dest] = newCost;
                    q.offer(new State(next.dest, newCost, cur.stops + 1));
                }
            }
        }

        return minCost[dst] == Integer.MAX_VALUE ? -1 : minCost[dst];
    }
}
```
![WhatsApp Image 2026-03-31 at 9 25 20 PM](https://github.com/user-attachments/assets/443b9500-223c-41c2-9376-0527040b1a52)
![WhatsApp Image 2026-03-31 at 9 22 50 PM](https://github.com/user-attachments/assets/745d60d4-50ac-46d4-bd98-b8acd41ba8a2)
