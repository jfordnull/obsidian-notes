AlphaGo meant to prefigure AlphaFold

Three subsystems: Policy (rules), Move-evaluation, "Creativity"

Knowledge of game is sequential, evaluating next move is episodic

Greedy systems don't think forward, consider next move

# Search

One of the most primitive operations of any intelligent entity, autonomous framework. Represents the pursuit of a goal through space. Most AI at its core involves searching through:
- States
- Assignments or values
- Orderings of a route
Uninformed or unsupervised search does not require *any knowledge of the problem domain*. A *brute-force* approach.

- We begin in some starting state, searching for a goal state (supervised state).
- We have some method of transitioning form the current state to one or more successor states. Transitions may have a cost associated with them (edge weight, travel time, etc.)
- Unsupervised search offers no method of selecting one transition over another for a given state
	- No fixed metric to tell us if we're getting closer to the goal until we're there
- Use some measurement (derived from purely local information, adjacent to current node) to make a selection from offered successor states
	- Said to employ a *greedy* algorithm

**Evaluating Search Methods**
