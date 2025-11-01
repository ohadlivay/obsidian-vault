
### Total Lag & Latency
#### Lag
how many documents are currently waiting to be handled. documents can pile-up up to a certain point - beyond that they might get overridden, ejected from the system or other bad things. 

#### Latency
How long did the document that was just handled wait for. this is a critical metric as it directly impacts [[Logz.io|logz's]] clients.

If lag goes up and latency goes down -> situation looks like it is getting better but the latency will soon go up again. 
If lag goes up and latency goes up -> situation is getting worse. lag is piling up.
If lag goes down and latency goes down -> situation is getting better and likely to resolve soon
If lag goes down and latency goes up -> latency will soon follow after lag pile-up is ingested.

### Log parsers/indexers
an [[ElasticSearch]] indexer which takes documents from [[Kafka]] and passed them through parsing for enrichment and saving on the data nodes. 


### Account Shipping Rate by Node / Shard
This metric shows all [[Node|nodes]] on the [[Cluster|cluster]] and the indexing rate at each node. We can also see the contribution each account made,  and on how many [[Shard]] and which [[Node|nodes]] he is spread across. 