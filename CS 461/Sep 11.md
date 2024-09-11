We lack a one-to-one mapping of linguistic semantic logic to machine symbolic logic.

# Properties of Task Environments
- Fully v. Partially Observable
	- Can sensors detect all aspects of environment relevant to the choice of action?
		- May be only partially observable due to noise, distance, inaccessibility; Degree of occlusion

**Belief is our construction of our environment when our observability is muted.**
- Essential to human mapping of perceptions > actions > expected changes in environment
- Starcraft 1 probe observability example: 
	- For AI to be competitive in adversarial game, it required full observability to match human player's partial observability

**Single Agent v. Multiagent**
- Is there more than one agent in the environment?
	- Do we classify other drives as agents or semi-random features in the environment?
		- Other agents change the stability of an agent's belief state
	- Are other agents cooperative or competitive? 
		- Multiple agents can actually improve each other, have a net positive symbiosis
		- Do hive-minds and structures of clustered agents exceed the capacities of single agents? (e.g. bees, ants)

**Deterministic v. Stochastic**
- e.g. Gravity is a reliable deterministic model of some physical process; We don't need to study examples to predict how gravity will behave in a future scenario
- Pattern from learned process v. pattern from inferred process
- Is the environment's next state completely determined by the current state (state history) and the action executed by the agent?
- Two kinds of randomness: partially observed patterns and truly non-deterministic states
	- A fully deterministic but partially observed environment *seems* stochastic.
	- Most systems begin disordered but converge on deterministic understanding of environment.  
	- (Stochastic describes probabilistic randomness, like noise.)
- Deterministic systems are about sequence

**Episodic v. Sequential**
- Does the agent need to remember the history of previous states (sequential), or just attend the current one (episodic)?
- Can this decision affect future ones?
- Sequential systems need additional context (memory); A process of a sequence of states
- Episodic systems are often called *greedy*
