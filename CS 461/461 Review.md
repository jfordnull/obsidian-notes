**Task Environments**

A "known" environment: An agent is aware of the "laws of physics" for the problem
- In a known environment, the outcomes (probabilities) of all actions are known
- Can still be partially observable (Example, Starcraft "fog of war"; environment partially observed but rules known)
An "unknown" environment: Actions must be tried to see what effects they have

(Fully) Observable: All relevant aspects of environment can be observed 
- Environments usually partially observable due to noise, distance, inaccessibility
Unobservable: No sensors

Single v. Multiagent
- Are other agents cooperative or competitive?

Discrete v. Continuous
- How are state and time handled? Steps or flow?

Nondeterministic: All possible outcomes are known but not their probabilities
Deterministic: Next/future state completely determined by current state and agent's action. (Probabilities known)
Stochastic: The transition to the next state depends on a random element in addition to the agent's action

Sequential: The history of previous states matters
Episodic: Only local/current state matters

Static: The environment will not change while the agent is deliberating, as opposed to Dynamic environment

Properties of algorithms:
- Correct: The algorithm can find a valid solution
- Complete: The algorithm can find every solution
- Optimal: The algorithm can find the "best" solution, however best is defined
- Optimally Efficient: The algorithm finds the solution at least as fast (big-O time-complexity) as any other
- Informed: The algorithm can guide itself in some way other than blindly generating every possible state (reducing search space)

---

**Search Algorithms**

**Uninformed/Brute Force (Blind) Algorithms**
- DFS:
	- Selects a branch, goes as deep as possible, backtracks if a solution is not found (recursive).
	- Exponential time-complexity. $O(bd)$ storage complexity. Exhaustive, complete, not optimal
- BFS:
	- Nodes visited in level order. (Therefore optimal; will return shortest path for uniform-cost search space.) Complete, like DFS.
	- Storage complexity is terrible. $O(b^{d+1})$ (b:=branching factor, d:=depth of solution)
- IDDFS:
	- Exhaustive DFS to a certain limiting depth, increasing depth if solution isn't found.

**Greedy Algorithms**
- Always selecting the path that looks best based on local information. Dijkstra's is an example.

**Beam Search**
- Only goes down part of the search tree at each level
- From start, all successors generated as for BFS. At each level we keep the best N candidates, generate all children from each; Again select the best N (or K, W) candidates

**A-star**
- Cost function: $f(x)=g(x)+h(x)$; Where $g(x)$ is actual cost and $h(x)$ is heuristic cost
- Complete, optimal, optimally efficient (examines fewer nodes than any other optimal search algorithm)
- Storage needs can still be large, depending on search space

**Other Search Heuristic Examples:**
- Hill-Climbing
	- Always choose the path that improves the heuristic function the most, i.e. *steepest ascent*. Main issue is that it can get trapped in a local maximum/optima ("foothills" problem). Doesn't look backward
- Uniform-Cost
	- Order nodes by cost/distance from origin. This is also the vanilla **Branch and Bound** method. Complete and optimal
- Best-First
	- Like hill-climbing (and BFS), but can recover from dead ends and false starts. Keeps a list of open nodes and sorts them, most promising first, by cost and heuristic (estimated distance to goal). (For ex. in a priority queue)

**Heuristics**
Algorithms will *always* produce a correct answer eventually, but often not efficiently. A heuristic will usually produce a correct (or approximate) answer, and much more quickly. Often they involve:
- Breaking a big problem up into subproblems. Sometimes we solve all these problems; sometimes a subset. 
- Working backward from a solution
- Identifying similar problems
- Successive approximation/iteration: can we find a state that is in some way "closer" to our solution?

AI problems are large and cannot be solved by straightforward algorithms within the lifetime of the universe. A more informed algorithm reduces the search space or scope of a problem. (The goal of all heuristics is to reduce search space.)

**Properties of Heuristics:**
- Admissible: Always results in optimal solution (if solution exists)
- Monotonic: As we progress, cost estimate should decrease. For our purposes, this is the same as saying it is consistent. (And that it also guarantees optimal paths to intermediate nodes.) Mathematically, a monotonic function moves in one direction, lacks concavity; A monotonic algorithm is always admissible
- Optimistic: Should never overestimate cost to goal, should underestimate cost to goal
- If two heuristics are admissible, and $h_1(n) < h_2(n)$, h2 is more informed for that node. If this pattern holds across the entire graph, h2 *dominates* h1, and is a better heuristic.

**Generating Heuristics**
- We can *relax* the problem: Remove restrictions on how we reach solution
- Random restart: If we reach a dead end, jump to a randomly chosen point in search space and start over
- Reduced problem: Try to solve subset of problem
- Pattern Database: Try several subsets, store and compare exact cost of each

---

**Constraint Satisfaction**

CSPs: Rather than searching through states, we search through possible assignments of variables.

CSPs are represented using a Constraint Graph: Each node represents a variable. Nodes edges represent a shared constraint. Each node has a domain of values that represent possible assignments
- We can apply search techniques/algorithms to this graph (e.g. DFS with Forward Checking and Constraint Propagation)
- We can search smarter by identifying which constraints are violated by a failed solution and focusing on those

More formally:
- Given a set of n variables: $V_1, V_2, ... , V_n$
- Each with a domain of possible values: $D_1, D_2, ... , D_n$
- And a set of k constraints on those possible values: $C_1, C_2, ... , C_k$
A solution is an assignment of values to variables, with each value being assigned to the correct domain for that variable
A "complete" solution assigns a value to all variables
A "consistent" solution satisfies all constraints
A "correct" solution is complete and consistent

An advantage of constraint satisfaction is that it's *general*. We can write a general constraint satisfaction solver and apply it to any problem (if formulated correctly)

**Constraints**
- Unary - Applies to 1 variable
- Binary - Applies to 2 variables
- N-ary - Applies to N variables
- Global - Applies universally
We also have softer *preference* constraints, which lead to a *preferred* states, by applying a *penalty* (cost) to other options.

**Constraint propagation:**

In CSPs, an algorithm can search (i.e. try another assignment of values to variables) using a type of inference called *constraint propagation*
- We use the constraints *already known* to reduce the number of legal values for a variable, which in turn limits possible values for other variables
- If we are choosing which variable to assign a value to next, we should choose the one with the fewest legal values (least entropy)

The key idea is *local consistency*
Node-Consistent: All values in the variable's domain satisfy the variable's unary constraints
- N-ary constraints can be decomposed into binary constraints 
Arc-Consistent: If every value in variable's domain satisfies variable's binary constraints
K-Consistency: For any assignment of consistent values to $k-1$ variables, a consistent value can be assigned to $V_k$

AC-3:
- Popular constraint propagation algorithm for arc-consistency. Works by maintaining a queue of arcs to consider. Binary constraints become two arcs, one in each direction.
- Worst case time-complexity: $O(cd^3)$

---

**Genetic Algorithms**
