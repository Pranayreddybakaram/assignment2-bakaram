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
---
This table shows the data related to my favourite food items. Which i would recommend others.

|FOOD|LOCATION|AMOUNT|
|---|---|---|
|Pizza|Pizza Hut|15$|
|Biryani|Bawarchi|30$|
|Burger|Mcd|2$|
|Pasta|Wall Mart|6$|



  int m, n;  
  vector<long long> dp_before(n), dp_cur(n);  

  long long C(int i, int j);

  // compute dp_cur[l], ... dp_cur[r] (inclusive)
  void compute(int l, int r, int optl, int optr) {
      if (l > r)
         return;

      int mid = (l + r) >> 1;
      pair<long long, int> best = {LLONG_MAX, -1};

      for (int k = optl; k <= min(mid, optr); k++) {
          best = min(best, {(k ? dp_before[k - 1] : 0) + C(k, mid), k});
      }

      dp_cur[mid] = best.first;
      int opt = best.second;

      compute(l, mid - 1, optl, opt);
      compute(mid + 1, r, opt, optr);
  }

  int solve() {
      for (int i = 0; i < n; i++)
          dp_before[i] = C(0, i);

      for (int i = 1; i < m; i++) {
          compute(0, n - 1, 0, n - 1);
          dp_before = dp_cur;
      }

      return dp_before[n - 1];
  }



  > In both contexts it refers to simplifying a complicated problem by breaking it down into simpler sub-problems in a recursive manner. While some decision problems cannot be taken apart this way, decisions that span several points in time do often break apart recursively. Likewise, in computer science, if a problem can be solved optimally by breaking it into sub-problems and then recursively finding the optimal solutions to the sub-problems, then it is said to have optimal substructure.

  [dynamic programming](https://en.wikipedia.org/wiki/Dynamic_programming)



    var m := map(0 → 0, 1 → 1)  
  function fib(n)  
      if key n is not in map m  
          m[n] := fib(n − 1) + fib(n − 2)  
      return m[n]  


[Code Source](https://en.wikipedia.org/wiki/Dynamic_programming)
