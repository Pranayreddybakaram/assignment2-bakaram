# assignment2-bakaram
# pranay bhargav reddy bakaram
### hyderabad
Hyderabad is the capital and largest city of the South Indian state of Telangana. It was ruled by the Qutub Shahis, Mughals and the Nizams which shaped its history. The city is noted for its monuments which includes the masterpiece of **Charminar** and the fort of **Golconda**.
---
## Travelling to my favourite place.
1. The fastest way to reach my favourite place is airways.
2. You need to got to kansas city using road transport.
   1. book a flight from kansas city to chicago airport.
   2. book another flight from chicago to Hyderabad.
* buy some food
  * choclates 
  * biscuits
* buy new clothes
* buy buy new shoes

**[AboutMe](AboutMe.md)**

---

## tables

This table shows the data related to my favourite food items. Which i would recommend others.

|FOOD|LOCATION|AMOUNT|
|---|---|---|
|Pizza|Pizza Hut|$15|
|Biryani|Bawarchi|$30|
|Burger|Mcd|$2|
|Pasta|Wall Mart|$6|

---

## Quotes I like

>The greatest glory in living lies not in never falling, but in rising every time we fall.
-*Nelson Mandela*

>The way to get started is to quit talking and begin doing.
-*Walt Disney*

---

## Code Fencing

 const int INF = 1000000000;
 vector<vector<pair<int, int>>> adj;

 bool spfa(int s, vector<int>& d) {
     int n = adj.size();
     d.assign(n, INF);
     vector<int> cnt(n, 0);
     vector<bool> inqueue(n, false);
     queue<int> q;

     d[s] = 0;
     q.push(s);
     inqueue[s] = true;
     while (!q.empty()) {
         int v = q.front();
         q.pop();
         inqueue[v] = false;

         for (auto edge : adj[v]) {
             int to = edge.first;
             int len = edge.second;

             if (d[v] + len < d[to]) {
                 d[to] = d[v] + len;
                 if (!inqueue[to]) {
                     q.push(to);
                     inqueue[to] = true;
                     cnt[to]++;
                     if (cnt[to] > n)
                         return false;  // negative cycle
                 }
             }
         }
     }
     return true;
 }

  > The Shortest Path Faster Algorithm (SPFA) is an improvement of the Bellman–Ford algorithm which computes single-source shortest paths in a weighted directed graph. The algorithm is believed to work well on random sparse graphs and is particularly suitable for graphs that contain negative-weight edges. However, the worst-case complexity of SPFA is the same as that of Bellman–Ford, so for graphs with nonnegative edge weights Dijkstra's algorithm is preferred. The SPFA algorithm was first published by Edward F. Moore in 1959, as a generalization of breadth first search; SPFA is Moore's “Algorithm D.” The name, “Shortest Path Faster Algorithm (SPFA),” was given by FanDing Duan, a Chinese researcher who rediscovered the algorithm in 1994.

  [Shortest Path Faster Algorithm](https://en.wikipedia.org/wiki/Shortest_Path_Faster_Algorithm#cite_note-duan-3)



      for each vertex v ≠ s in V(G)
          d(v) := ∞
      d(s) := 0
      push s into Q
      while Q is not empty do
          u := poll Q
          for each edge (u, v) in E(G) do
              if d(u) + w(u, v) < d(v) then
                  d(v) := d(u) + w(u, v)
                 if v is not in Q then
                     push v into Q

[Code Source](https://en.wikipedia.org/wiki/Shortest_Path_Faster_Algorithm#cite_note-duan-3)
