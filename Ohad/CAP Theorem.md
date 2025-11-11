![[Pasted image 20251111174005.png]]
need to understand it, and implications of it on big data. (!)

"It is impossible for a web service to provide more than two guarantees at the same time:
1. [[Sequential Consistency|(Sequential) Consistency]]
2. availability
3. partition-tolerance

Consistency:
	Every node sees the same data at the same time. After an update, all clients read the same, latest value.

Availability:
	Every request (read/write) receives a response, even if some nodes are down.

Partition-tolerance:
	The system continues to operate even if communication between nodes is lost (network partitions).


why can't we guarantee all 3?
(proof in lec3 (!))

C in CAP != C in ACID
as cap's C means [[Sequential Consistency]] and in ACID it refers to the data schema constraints.

CP and AP are best, CA is unfeasable (a car will EVENTUALLY get a flat tire and needs to survive it). P is unavoidable. 
AP exampe: DNS. consistency not prioritizied. its ok to make mistakes - availability is whats important.
CP - fintech prefers CP, mission critical. cant make wrong transaction - costs money! 
CA - cdn? like netflix?

Choosing between C  and A is a tradeoff. can be dynamically chosen according to situation: for airline company when there are many seats, its ok to choose AP. once there are few seats left - CP overtakes.

Types of consistency
	* Strong consistency: after writing, any reads will read that value.
	* weak consistency: cannot guarantee. might return old value.
	* eventual consistency: eventually it will be strong consistency.
		* causal consistency: processes that have causal relationships will see consistent data. user will not read effected data without causal data.
		* read-your-write consistency: a process who wrote will be able to read new value.
		* session consistency: as long as session persists, system guarantees read-your-write consistency.
		* monotonic read consistency: ...
		* monotnic write consistency: ...

Partitioning strategies:
some parts of a system can be either CP or AP.
