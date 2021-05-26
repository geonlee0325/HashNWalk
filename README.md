## HashNWalk: Hash and Random Walk Based Anomaly Detection in Hyperedge Streams

*Given a stream of hyperedges from a time-evolving hypergraph, how can we detect structurally or temoprally anomalous ones? Can we detect them in near real-time using constant space?*

Sequences of group interactions, such as emails, online discussions, and co-authorships, are ubiquitous; and they are naturally represented as a stream of hyperedges (i.e.,  sets of nodes). Despite its broad potential applications, anomaly detection in hypergraphs (i.e., sets of hyperedges) has received surprisingly little attention, compared to anomaly detection in graphs. While it is tempting to reduce hypergraphs to graphs and apply existing graph-based methods, according to our experiments, taking higher-order structures of hypergraphs into consideration is worthwhile.

We propose HashNWalk, an incremental algorithm that detects anomalies in a stream of hyperedges. It maintains and updates a constant-size summary of the structural and temporal information about the input stream. Using the summary, which is the form of a proximity matrix, HashNWalk measures the anomalousness of each new hyperedge as it appears. HashNWalk is **(a) Fast:** it processes each hyperedge in near real-time and billions of hyperedges within a few hours, **(b) Space Efficient:** the size of the maintained summary is a user-specific constant, **(c) Effective:** it successfully detects anomalous hyperedges in real-world hypergraphs. 

### How to run
The datasets should be prepared in following format. Each hyperedge is represented as:

	[nodes] <tab> [timestamp]
	eg) 0,1,3,5\t2345

To run the code with a toy dataset, execute:

	./run.sh

You can set the hyperparamters in lines 20-22 in main.cpp.

	- K: number of hash functions
	- M: number of supernodes
	- alpha: time decaying parameter
