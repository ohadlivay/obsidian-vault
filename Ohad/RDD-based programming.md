Spark Context: driver that is knows the cluster state. 

RDD - a data structure that is Immutable Distributed Collection
Each RDD is split to partitions for parallelization.
RDD Operations:
* transform:
	turn 1 RDD into another (copy, transform, save)
	computed lazily; 
	keeps track of dependancy using a lineage graph. at split node, caches (cause it will be reused). 
	failure is easily recovered, can start from failed node.
	per job
* action


(! persistance and cache - for test