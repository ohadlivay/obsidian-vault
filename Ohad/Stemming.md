cutting the inflected words to their root form
e.g
create, created, creating, creator, creativity -> creat


use heuristics to turn to stem. 
created -> creat

problem is that word with different meaning will also be put into the bin, meaning stemming is too general.

Algorithms to stem:
* Porter Stemmer:
	* sses -> ss
	* ies -> i
	* ational -> ate
	* tional -> tion