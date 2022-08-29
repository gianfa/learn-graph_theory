# Graph Theory Concepts

## Contents:
* [Basic definitions](#basics)
* [Centrality measures](#centralities)
* [Resources](#resources)


## <div id='basics'>Basic definitions</div>

### <div id='connectivity'>Connectivity</div>
A graph is connected if all its nodes have at least one connection to another 
node.


### <div id='shortest_path'>Shortest Path</div>
https://en.wikipedia.org/wiki/Shortest_path_problem  
> A path is a sequence of verices $P=(v_1, v_2, ..., v_n) \in V \times V \times... \times V$
such that $v_i$ is adjacent to $v_{i+1}$ for $1 \leq i \lt n$. Such a path is
called a path of length $n-1$ from $v_1$ to $v_n$.  

The *shortest path* from $v$ and $v'$ is the path $P=(v_1, v_2, ..., v_n)$, 
where $v_1=v$ and $v_n=v'$ that minimizes the sum $\sum_{i=1}^{n-1} f(e_{i, i+1})$,
with $e_{i, i+1}$ being the edge incident to both $v_i$ and $v_j$.


## <div id='centralities'>Centrality measures</div>

> The [**degree centrality**](https://networkx.org/documentation/stable/reference/algorithms/generated/networkx.algorithms.centrality.degree_centrality.html#networkx.algorithms.centrality.degree_centrality) for a node v is the fraction of nodes it is connected to.  
The degree centrality values are normalized by dividing by the maximum possible degree in a simple graph n-1 where n is the number of nodes in G.

$n_i/n_{max}; \qquad n_{max}=max(n_j), j \in \{0, 1, ..., N\}$

> [**Closeness centrality**](https://networkx.org/documentation/stable/reference/algorithms/generated/networkx.algorithms.centrality.closeness_centrality.html#networkx.algorithms.centrality.closeness_centrality) of a node u is the reciprocal of the average shortest path distance to u over all n-1 reachable nodes.
$ C(u)=\frac{n-1}{\sum_{v=1}^{n-1} d(v,u)}$.   


$d(v,u)$ is the shortest path distance between $v$ and $u$.

The normalized aveaged shortest path length is its reciprocal ("What's the average number of archs between it and all the other nodes, over the number of nodes?").

> [**Betweenness centrality**](https://networkx.org/documentation/stable/reference/algorithms/generated/networkx.algorithms.centrality.betweenness_centrality.html#networkx.algorithms.centrality.betweenness_centrality) of a node $v$ is the sum of the fraction of all-pairs shortest paths that pass through $v$.
$$c_B(v) = \sum_{s,t \in V} \frac{\sigma(s,t|v)}{\sigma(s,t)}$$  
where:
* $V$ is the set of nodes,
* $\sigma(s,t)$ is the number of shortes $(s,t)$-paths,
* $\sigma(s,t|v)$ is the number of those paths passing through some node $v$ 
other than $s,t$. If $s=t$, $\sigma(s,t)=1$, and if $v \in s,t,\sigma(s,t|v)=0$.



> [**Eigenvector centrality**](https://networkx.org/documentation/stable/reference/algorithms/generated/networkx.algorithms.centrality.eigenvector_centrality.html#networkx.algorithms.centrality.eigenvector_centrality) computes the centrality for a node based on the centrality of its neighbors. The eigenvector centrality for node  is the -th element of the vector  defined by the equation $Ax = \lambda x$.
  

[**Group Centrality Measures**](https://networkx.org/documentation/stable/reference/algorithms/centrality.html#group-centrality) are centrality measures referred to
a group of nodes, belonging to the network. The same definition above hold for
such a group of nodes.



## <div id='resources'>Resources</div>
1. [Algorithms, Networkx official docs](https://networkx.org/documentation/stable/reference/algorithms/index.html)
2. [Graph Theory, Wikipedia.org](https://en.wikipedia.org/wiki/Graph_theory)




