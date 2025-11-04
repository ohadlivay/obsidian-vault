![[Pasted image 20251104171929.png]]

based on [[Functional Programming]]

MR is used to solve complex problems like log analysis, pagerank computation, social graph analysis, sensor data analysis etc. 

map - function to transform data. returns a set of (key,value)
reduce - aggregates (like group by) over each set of (key,value)

these functions are sent to nodes containing the data such that the computation is done on-premise. 

pipeline:
Map --> Shuffle & Sort --> Reduce

shuffle phase - after mapped, we shuffle the output so it balances the load. 

it is important that the map and reduce functions have no dependencies between one another. this means it can be parallelized. 

any data structure can be used here.

map(key,value):
	//key: offset of the word in the file
	//value a word of the input document
	emit(value,1)

reduce(key,value)
	occurrences = 0
	for each c in values
		occurrences+=c
	emit key(key,occurrences)

search can be done aswell

in terms of complexity, it keeps linearity and is [[horizontal scaling|horizontally scalable]]. this paradigm keeps compute close to the data (data locality), so you're not limited by the network bandwidth. 