# Notes
> 2024.09.24

## Basics
Start by explaining the specifics of the environment and infrastructure.  Let's find some examples (in the Flatland paper, in the Routing/Scheduling paper) to build off of.  When it comes to the structure of the environment, we'll have a few options to choose from:
* a lattice grid
* a graph
	* in which cells are nodes
	* in which nodes are between cells
* a layered graph
* a hypergraph

Key tips:
* keep it as simple and minimal as possible
* don't impose behavior of agents on the structure of the environment
* we may not want to keep the blank cells

The way I can figure these things out is by plaing around with some examples.  Consider a few "candidate solutions", i.e. a list of cells and come up with which properties would be necessary to verify whether this is valid:
* connectedness (the two nodes must share an edge)
* direction (the agent must be able to move to that node when facing that direction -- legal transition)

For the agents, the static facts that are true from the start (initial conditions) should comprise our instance.  Keep this simple and precise.  This will be things such as:
* initial direction
* starting position
* target position

## Being descriptive
We need a precise, unambiguous way of describing qualities of the environment.  A language such as mathematics can help us do that.  When possible, find an existing (or similar) math concept that has already been clearly defined and described.

In the case of the Flatland environment, we have well-defined properties of a graph to draw from.  We can clearly describe connectivity and direction.  If described as a graph, we may want to include the footnote that Flatland internally represents the environment as a grid.

We can structure the description in the following way:
* Base model (keep this simple and precise)
	* graph
	* agent
* Instance
	* initial characterization (initial direction, position, target)
* Formalization
	* what is a solution?
		* for an agent there is a path
		* what is a valid trajectory? (based on direction, position, legal transition)
	* collisions (conflicts)
	* fluents
	* anything that changes as the simulation runs
	* constraints

## Proposed outline
1. Graph
2. Agent
3. Solution (path)
4. Remaining formalization

Follow this tip:
* explanation
* definition
* constraints
