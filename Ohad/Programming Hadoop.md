How to write [[MapReduce]] programs in [[Apache Hadoop|Hadoop]]
([[BD_HW]] - hw1 will be posted next week probably)

written in [[Java]]

# Three parts
1. Driver class- component that coordinates between map and reduce., calculates analytics and starts all code (main function) submits job to Hadoop cluster. the driver runs on the developer side, the mapper and reducer will be ran on the nodes. also configures the Job.
	run()
	configures job; give name format, input format, output format, define mapper and the type off inputs and outputs it has.
	reducer; name, its inputs and outputs. 
	number of reducers.
2. Mapper class- using inheritance: run in cluster (!) output will not be available to us! map(key,value). generic, as its types is defined by driver. 
	map()
	process input (key,value) using standard java
	emit (key,value).....
3. Reducer class- using inheritance: run in cluster (!) output will not be available to us! reduce(k,list of values). writes (k,v) to  hdfs. reducer groups by key, thus shrinking list of fitting values. generic, same logic as mapper.
	reduce()
	calculate aggregations.
# Terms 
Hadoop Job - takes our jar file and combines with Hadoop.
Task - single task of mapper or reducer on a slice of data.
many tasks per job.
Input split: fixed size piece off input data, approximately size of [[Apache Hadoop#HDFS|hdfs]]

intermediate results are collected in HDFS. they will be shuffled, sorted and eventually reduced. after that they are deleted.

to maximize parallelism, Hadoop gives each mapper exactly one Input split. 

each (k,list of values) is handled by a single reducer. 

# Data types
hadoop needs its own types to ensure some functionalities
org.apache.hadoop.io.Text: like java string
org.apache.hadoop.io.IntWritable like int
org.apache.hadoop.io.LongWritable java long
org.apache.hadoop.io.FloatWritable java float
etc...
can define our own types, need to implement org.apache.hadoop.io.Writable and org.apache.hadoop.io.WritableComparable interfaces. 

# InputFormat
abstract class that tells hadoop how to treat the input file. 

we can just use TextInputFormat or KeyValueTextInputFormat. presets.

TextInputFormat: splits by lines. each row fed to mapper. k=row, v=the position in file in chars. 

OutputFormat - exactly the same just reverse order
# Word count example
parameters for application:
1. number of instances of reducer
2. input file path
3. output file (???)

	Combiner - aggregator between mapper and reducer to reduce network traffic. only works on associative and commutative functions.

# MapReduce patterns
some problems cant be solved with MR. some can:
## Summation Pattern
goal is to aggregate on groups
useful for statics (count, min, max, count per group, std etc..), inverted index.

structure:
mapper - key for group by, value is what we want to aggregate.
reducer - performs the aggregation about getting the group tuples.

Inverted index: map from term to documents containing it
Counting: 

## Filtering pattenrs
used for top k.//(???)

mappers: filter by key or value

top k : each mapper finds top k. cleanup to get top k from n mappers.
can be used for KNN
just one reducer possible (single point of failure) ! 

## Data organization pattern
### Binning
tell driver multiple outputs
and the each mapper tell it to send to correct bin

## Shuffling
key will be randomly picked number such that many values are mapped from the same key
value is our input record

## Meta patterns
job chaining, important(!). 
tell driver

## Join pattern
same as relational algebra. reduce vs map side join
reduce side join: one mapper per table, key is the join clause (A.bid=B.bid), value is the conctacted value. then reducer gets the groupby bid and emits the concated value (the join).
map side natural join: when one table is large and another is small (can be placed in one node memory). small map will be used in setup, and then large table would join with small map (cached) and emit the product.
