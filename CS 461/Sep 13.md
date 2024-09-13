Sequential Agents:
- Require residual memory to make correlates; Memory has a decay or half-life to it

**Properties of Task Environments**
- Static v. Dynamic Environment
	- Everything is bolted to the floor. Environment doesn't change with time. Pure static environments exist only in virtual spaces. Systems fall on a spectrum between static and dynamic. A building is relatively static temporally. 
	- Dynamic elements need to be tracked. This is where belief comes into agent decision-making process; Agent compares belief to new environment to determine what's changed
	- Chess is semi-dynamic. Sudoku is static.
- Discrete v. Continuous
	- How are *state* and *time* handled? Discrete steps or continuous (infinitely sub-dividable, functionally infinite) flow?
		- Some sensors discretize a continuous property; Some input is discrete but treated as continuous (e.g. digital video)
- Known v. Unknown
	- The agent's knowledge about the "laws of physics" related to a task
		- In a known environment, the outcomes/probabilities of all actions are known
		- An unknown environment must be explored, or actions tried, to see what effect they have
		- e.g. Case Testing for edge cases is an attempt to make environment known
		- Rules of environment could be programmed or learned through the agent's interaction with environment
	- A known environment can still be partially observable
		- e.g. Fog of war in a game; (Rules are known)