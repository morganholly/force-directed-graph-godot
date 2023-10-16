# force-directed-graph-godot
is a simple implementation of a [Force-Directed Graph](https://en.wikipedia.org/wiki/Force-directed_graph_drawing) (or FDG for short) in the Godot Engine.


## What is a Force-Directed Graph?
> Force-directed graph drawing algorithms are a class of algorithms for drawing graphs in an aesthetically-pleasing way. (Wikipedia)

The graph is a physical simulation of a system of bodies (nodes) connected by springs (edges). The system is simulated by applying forces to the nodes and springs and then updating their positions.

`force-directed-graph-godot` uses an implementation of the method showcased in [this incredible lecture by David Dobervich](https://www.youtube.com/watch?v=PTBuq0CXpWs).


## Usage
### Setup
1. Add a `ForceDirectedGraph` node to your scene.
2. Add `FDGNode` nodes as children of the `ForceDirectedGraph` node.
3. Add `FDGSpring` nodes as children of the `FDGNode` nodes.
4. Connect the `FDGNode` nodes with `FDGSpring` nodes by setting the `node_start` and `node_end` properties of the `FDGSpring` nodes.
5. After adding new Nodes or Springs, click the `Update Graph` button on the `ForceDirectedGraph` node to update the graph.

> Warning you might have to **reload** your scene after adding new nodes to the graph, if `Update Graph` does not work.

### Nodes
![Alt text](addons/force_directed_graph/icons/ForceDirectedGraph.svg)
**ForceDirectedGraph**<br>
The main node of the graph. It is responsible for updating the positions of the nodes and springs. 

![Alt text](addons/force_directed_graph/icons/FDGNode.svg)
**FDGNode**<br>
A node that is part of the graph. Can have different physical properties, such as speed, drag, radius, mass, etc.

![Alt text](addons/force_directed_graph/icons/FDGSpring.svg)
**FDGSpring** extends `Line2D`<br>
The connection betweend two `FDGNode` nodes. The `node_start` and `node_end` properties must be set to the `FDGNode` nodes that should be connected by this spring.


## Example
![Example graph](example/example_graph.PNG)
You can find this example graph in the `example` folder of the project. It uses a basic setup of `FDGNode`s and `FDGSpring`s including one custom node (the big Godot Logo).


## Common questions and problems
**Q:** Why are the nodes not moving in the editor?<br>
**A:** You can disable editor simulation on the `ForceDirectedGraph` node.

**Q:** Why are the connection lines looking so jagged?<br>
**A:** Try activating 2D anti-aliasing on the `FDGSpring` nodes AND in the project settings.


## Documentation
For additional information, please refer to the documentation generated by the Godot Engine (F1) or dive into the source code yourself.
