---
title: "Force Directed Graphs"
enableToc: false
date: 2022-11-17
tags:
- Visualization
- Software
---

We'll construct a Force Directed Graph from the ground up using D3.js.


# Initializing the graph

First we'll initialize a graph with arbitrary nodes and links. The nodes will have some kind of identification and the links will have a source and target.
```
var graph = {
  nodes: [
    { name: "A" },
    { name: "B" },
    { name: "C" },
    { name: "D" },
    { name: "E" },
    { name: "F" },
    { name: "G" },
    { name: "H" },
  ],
  links: [
    { source: "A", target: "B" },
    { source: "B", target: "C" },
    { source: "C", target: "D" },
    { source: "D", target: "E" },
    { source: "E", target: "F" },
    { source: "F", target: "G" },
    { source: "G", target: "H" },
  ],
}
```
# Initializing the simulation 
Now, we need to start the simulation, meaning we need to give each of our nodes an x and y position, velocities in the x and y direction, and z-index values. To make these values meaningful, we need to apply forces: center force, charging force (repulsion/attraction), and link force. We'll also need to define the tick function, which will be called on every tick of the simulation. This function will update the position of each node and link. 

```
var simulation = d3
  .forceSimulation(graph.nodes) // initialize the simulation with the nodes
  .force(  // center force
    "link", // add a link force
    d3.forceLink(graph.links).id(function (d) { // set the id accessor to return the name of each node
      return d.name // set the id of the link to the name of the node
    }),
  )
  .force("charge", d3.forceManyBody().strength(-30)) // add a charge force
  .force("center", d3.forceCenter(width / 2, height / 2)) // add a center force
  .on("tick", ticked); // call the ticked function on every tick of the simulation
```



