**Common AI Implementation Spaces**:
- Hyper-personalization
- Recognition
- Conversation & Human Interaction
- Predictive Analytics & Decisions
- Goal-Driven Systems
- Autonomous Systems
- Patterns & Anomalies

**Machine-Learning**
- Attempts to create understandings of natural world through mapping connectivity of huge sums of data; Abstraction framework. 

**AI Methodology**
- Modeling of consciousness, machinery of thought. Goes back to Ancient Greeks. 
- Algorithmic framework at its core. Conditional, sequential, like all programming, but some additional autonomous decision-making capacity given environmental changes distinguishes AI. 

# Agents, Environments, and Perception

**Agent**: Anything that can be viewed as perceiving its *environment* through *sensors* and acting on that environment through *actuators*:
- Auto-pilot: drones, rumbas, etc.
**Percept**: The agent's perceptual input at a given instant
**Percept Sequence**: Complete history of percepts
- Choice of action can depend on percept or percept sequence, but not on anything it has not observed yet.
Agent's behavior is described by an **agent function** that maps percepts or percept sequence to actions.
- Agent function does not base its actions on the environmental state, only on what has been *perceived* about that state
	- Percept-memory allows for temporal knowledge-building, causal inference; Just because I can't see something *now* doesn't mean I haven't seen it before.
	- e.g. The QR code identification in your iPhone's camera app: An agent perceives your camera for anything matching the paradigm of a QR-code; Agent function maps the percept to an action (bring up the QR-code link).
- Implemented by an **agent program**
- Conceptually: a table lookup or set of if-then rules; most implementations are more complex

Tensor: Matrix of matrices; From Wikipedia: 
```
In mathematics, a tensor is an algebraic object that describes a multilinear relationship between sets of algebraic objects related to a vector space.
```
# What makes an agent 'rational'?

- One definition: an agent that does the right thing, with the proper "then" action for every "if" state
	- What does doing the "right" thing mean?
- System should be consistently rational to be 'rational'
- We consider consequences
	- Can't control for all output scenarios; How does the system respond when dysfunction occurs?
	- Must consider unintended edge cases, human fault
- The right action is one that leads to desired outcome based on the series of environmental states produced by interacting with the environment
	- Avoid deadlock states
	- Agent should be able to explore its environment and gather new information/percepts
- Better to define goal state in terms of what is wanted, not how agent should behave

RISC v. ARM architecture: generalization v. application-specific (and thus more efficient) instruction sets