**Best-First Search**

Microorganisms are "greedy"; Think instinct, firmware of intelligence.

**Beam Search**
- Useful if we have threading capacity. Focuses a search by only going down part of the search tree at each level (divide and conquer.)
- From the start state, all successors are generated as for BFS
- The best W are selected
- For that W, all successors are generated, and the best W of those successors are generated
- In general a wider beam (larger value of W); But computationally massive as branching factor approaches infinity