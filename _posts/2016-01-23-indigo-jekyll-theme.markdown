---
title: "The Modified Traveling Salesman Project"
layout: post
date: 2018-05-02 22:10
tag: np-hard
image: https://koppl.in/indigo/assets/images/jekyll-logo-light-solid.png
headerImage: false
projects: true
hidden: true # don't count this post in blog pagination
description: "This was a project for my Algorithms course: CS170. The project specification can be found [here](../assets/cs170-spec.pdf)."
category: project
author: rishab231
externalLink: false
---

![The Modified Traveling Salesman Problem](../assets/images/map.png)

This was a project for my Algorithms course: CS170. The project specification can be found [here](../assets/cs170-spec.pdf).

This was a modified version of the famously intractable Traveling Salesman Problem (TSP). Given an input graph where each vertex represents a kingdom, and there exist edge weights as well as vertex costs for each kingdom; our task was to design and develop an algorithm that <b>conquers all kingdoms (vertices)</b> while minimizing the <i>Total Cost</i> = ∑ Conquering costs + ∑ Traveling costs.

This project was trickier than the TSP because of certain special rules that the project allowed:
- Once you conquer a kingdom, all its neighbours are automatically conquered.
- Kingdoms can be visited without conquering them.
- One must begin and end the tour at the starting kingdom given to us.


<b>The algorithm:</b>

We utilized a two-part approach to derive a solution given an input instance:
	- Finding the set of <i>special</i> nodes to conquer
	We used a greedy strategy with multiple heuristics to approximate the minimum weighted set cover (i.e. given a graph with vertex weights, finding the minimum weight that covers the entire graph). Our heuristics include combinations of <i>max_neighbours</i>, <i>average_edge_cost</i>, <i>min_conquering_cost</i>, et al.
	- Generating a cheap tour through these special nodes</b>
	Once we have determined our set of <i>special</i> nodes, we generate the cheapest possible tour through these subset of vertices. We used a number of approaches to approximate the best possible tour through these vertices:
		- Creating a <i>Steiner Tree</i> of the special nodes and running all pairs shortest path to generate a tour from the starting vertex
		- Reducing the problem to Metric-TSP by adding heavy-weighted dummy edges to make the graph complete; we then use <i>Christofides</i> algorithm
		- We also tried to use a greedy approach by running Dijkstra's algorithm from every special node and greedily adding the closest special node to the tour
	
---