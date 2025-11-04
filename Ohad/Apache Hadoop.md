open-source framework that embodies the [[MapReduce]] model.
## HDFS
Hadoop Distributed File System
a component that knows how to manage files across multiple nodes. sits at the batch layer in 
### Splitting documents
documents are broken into blocks and distributed throughout different nodes. a replica of each document shard (or block) is saved on different nodes for robustness. 
### Replicas
if we expect 2 faulty nodes on our cluster at most at any given time, then we will set number of replicas to 3 such that we're protected from loss. ensures persistence, availability. 

### Blocks
data split into blocks. each block stores data from a single data source. blocks (or chunks) are sized 64Mb, so we can have some waste: if a file is sized 129Mb, it requires 3 chunks. (64+64+1=129)

### Master Node
- stores the HDFS metadata
- might be replicated
- clients applications get access through HFS API's.