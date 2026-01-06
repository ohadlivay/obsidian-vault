### problems:
doesn't work well with too many receivers 
tightly coupled
client has to wait for response


## Event driven model
![[Pasted image 20251216173836.png]]
less coupled since generators have to know only distributor, not every consumer. 
works even if client is offline
problem with ensuring message received - solved by message broker. 

### Point to point
tightly coupled, $O(n^2)$ complexity

### Apache Kafka
1. a distributed pub-sub messaging system
2. designed for real time activity streaming data (log, metrics, collections, social media, streams,..)
3. manage feed in **topics**. 
4. can scale consumers of certain topics easily

#### Components
1. Producer: entity that publishes data to kafka cluster, made of brokers. 
2. Broker: distribute the messages (receive and publish to subscribers)
3. Consumer: receives data from broker 

#### Offset - https://gemini.google.com/share/94021ceacf22


#### Concepts
1. Topic - a category to which records are stored and published.
2. each topic is divided to Partitions. (allows parallelism)
3. partition is an ordered queue (by the order of arrival from brokers) ordered as FIFO (guaranteed PER partition only)
4. every message is given a sequence number 
5. Consumers subscribe to topics. 

Consumer groups main goal is fault tolerance (Kafka ensures only one consumer consumed at a time). a good side effect is we ensure an action is performed once (like charging on credit card)

