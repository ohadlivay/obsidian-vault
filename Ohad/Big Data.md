# Lecture 1
## Syllabus
lectures combine theory and hands-on.
### outline
lec 1: whats is big data + course logistics
lec2-8: process big data using mapreduce, spark (hw on these technogolies). 
lec 9-11 nosql
### Logistics
3 HW's in pairs or triples. 10% towards final grade. artem checks them himself. 
### Quiz
do not miss deadlines! quiz meant to check class level. ez points.
20 questions, multiple choice (?).

## Intro
big data is about size and uses of the data. big data systems need to operate in decent complexity time. 

### Four V's of Big Data
Volume - how much data
Variety - how many formats of data
Velocity - how fast the data is being processed
Veracity - quality of data

### Big Data Value Chain
Generation -> Acquisition -> Storage -> Analysis
Generation: the sensors
* passive recording: structured data is stored. 
* active generation: semi structured or unstructured. user generated.
* automatic production: sensor, timeseries
Acquisition: the system that collects it
* Collection: 
	* pull based (web crawl)  as it is pulled by the system. 
	* push based (video surveillence) as it is pushed into system
* transmission: high velocity link
* pre processing: cleaning, integrating, redundancy elimination.
Storage:
* infrastructure: HDD, SDD.. or network architecture: DAS,NAS,SAN.. like amazon s3 object storage.
* data management: 
	* file systems ([[HDFS]])
	* key-value (Memcached)
	* column-oriented db (Cassandra)
	* document db (MongoDB)
* programming models: [[MapReduce]], stream processing, graph processing. 
Analysis:
* Objectives:
	* predictive/prescriptive/descriptive analytics. 
* Methods
	* statistical
	* data mining
	* ml methods (clustering, classification, regression)
Diverse domains call for customized techniques!


### Big Data Challenges
* tech and infrastructure: old infra and software couldn't handle the ever increasing data needs. so  new architectures to support data applications at scale were developed.
* data management and analysis: new focus on data. gave birth to Data science. 
### Speed (Latency) matters
memory -> minute
network -> weeks
flash -> months
disk -> decades

### The Bottleneck
is usually in how fast we can load data into the cpu. 
Solution: dont transfer data to cpu, transfer cpu to data.
basically means that each data node will also have cpu power. hence minimizing data transfering, handling bottleneck with parallel processing. 
example: [[MapReduce]]

### Google Flu
outbreak was detected in google trends 2 weeks before outbreak.
Nowcasting(?)

### Use-cases/Example of big data
* john snow - first recorder use of big data: he clustered cases of cholera, found each cluster centered around water source and helped mitigate a plague.
* house of cards - scriptwriters wrote scripts using previous episode user comments and feedback. 
# Lecture 2
## Lambda Architecture
tools that provide scalable systems for lots of data.
* Batch Processing
process big data at rest
* Real-time processing
data in motion
* Interactive exploration

### Predictive analytics and ML
### When to use such architecture?
* too much data for traditional db's
* unstructured data for analytics and reports
* want to analyze unbounded streams of data in real time with low latency.
![[Pasted image 20251028184324.png]]
(https://learn.microsoft.com/en-us/azure/architecture/databases/guide/big-data-architectures)

### Lambda Architecture Requirements
* fault tolerance
* support variety of usecases
* linear scale-out capabilities
* extensible
### Lambda Query
query = function(all data)
properties:
latency - how long to run. 
timelines - how fresh and consistent data is
accuracy - tradeoff between performance and scalability. approx.

### Lamba Architecture paths
* cold path (batch layer) - stores all incoming data in raw form and perform batch processing.
* hot path (speed layer) - analyze data in real time. low latency at expense of accuracy.

### Diagrams
![[Pasted image 20251028190652.png]]
Master data- the canonical, raw data. ground truth.
![[Pasted image 20251028191037.png]]
()
![[Pasted image 20251028191124.png]]
()

## Big Data Challenges
### Data volume
data increases exponentially. 
### Failures
bugs, crashes, outages, hardware failure... need replicas, coordination, rebootability and recoverability. 
### Network bandwidth
network becomes bottleneck if we need to move lots of data. 
[[MapReduce]] approach is to not transfer all data, but to bring CPU to data using a data node (Server

## [[Scaling|Scalability]]

## [[Apache Hadoop]]
# Lecture 3
[[CAP Theorem]]
[[Progamming Hadoop]]
# Lecture 5
[[Docker Containerization]]
[[Spark]]
# Lecture 6
[[RDD-based programming]]
# Lecture 7
[[Distributed pub-sub]]

# Lecture 8
[[Spark SQL]]
# Lecture 9
[[Big Data for ML]]