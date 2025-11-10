We want to retrieve the best data for each query. that means we need some kind of way to rank how relevant each document in the corpus is to our query. but how to measure importance? 
# TL;DR
boolean_score - 1 if term in doc, else 0
tf_score = count of term in doc
log tf score = same but weaken effect of big documents
tf-idf score = take into account term frequency and term importance.
bm25 score = take into account tf, term importance and document length.
# Using boolean count
allows to count terms in common. very strict and such queries might not behave how we'd like.
# Using Term-Frequency
or TF. use the frequency of terms to rank importance. 
### Log(TF)
using a [[Logarithm]] on the tf forces less importance to high frequencies, but low matching documents. diminishing returns.
e.g
a document containing 1000 'Elon musk' is not 10 times as far as a document containing 100 times 'Elon musk' is from a document containing 0 'Elon musk's.

problems: 
* the bigger the document, the more probable it is to be picked.
* words were not weighted for importance, all equal.

### Term Importance using IDF
document frequency - how prevalent is the term in all corpus. 
Inverse document frequency - how rare is a term in all corpus.
$IDF_{t}=\log\left( \frac{N}{df_{t}} \right)$
a term appears in 60% of documents, it is less important than a term that appears in 3% of documents.
this will be used as a multiplier for word frequency. 
### TF-IDF
$Score(q,d)=\sum_{t \in q \cap d}TF*IDF_{t,d}$


# Using Vector Spaces
we essentially create a [[Bag of Words]] where each term is an axis. each vector will have count in which each word appears in each document. this can help us rank which document is more related to our query using different measuring techniques. 
documents in [[Corpus]] are turned into [[Vector|vectors]] such as in a [[Bag of Words]] model.

Problems:
* dimension problems since matrix is sparse as most words do not appear in most documents. 
* no importance given to order of words

# Distance metrics
we want to find the documents which are closest to query to assist in our document retrieval ranking task. how to measure this distance?
### L norms
#### Euclidean 
$\left( \sum_{i=1}^n |x_{i}-y_{i}|^p\right)^{1/p}=\sqrt{ \sum_{i=1}^n(x_{i}-y_{i})^2 }$
where $p=2$
example:
$V_{1}=[1,7,9]$
$V_{2}=[11,21,4]$
Distance($V_{1},V_{2}$)=$\sqrt{ 100+196+25 }$=cool number
gives more importance to the large differences between terms.
#### Manhatten distance
$\left( \sum_{i=1}^n |x_{i}-y_{i}|^p\right)^{1/p}= \sum_{i=1}^n(x_{i}-y_{i})$
where $p=1$
basically the sum of differences. gives equal importance to all terms.
#### Chebyshev distance
$\lim_{ p \to \infty }$
essentially a max function
### Cosine Similarity
$Sim(\vec{x},\vec{y})=\frac{{\vec{x^T}\vec{y}}}{||\vec{x}|| * ||\vec{y}||}$
given two vectors from the OOB matrix, where frequencies are counted, it calculates the angle between them. this ignores raw magnitude as they are scaled down (the numerator), solving the bias towards big documents problem we had before. 
# BM25
Best-Match 25 is an mathematical model to score document relevancy while penalizing big documents. how much to penalize? adjust b hyper-parameter.

avdl =  average document length
$B=\left( (1-b)+\frac{b{dl}}{avdl} \right)$
such that $0\leq b\leq_{1}$
so if $b=0$ we give no weight to the document length
and if $b=1$ we give all the weight to the document length.

Score=$\sum_{i\in q}\log \frac{N}{df_{i}}{\frac{(k+1)tf_{i}}{k\left( (1-b)+\frac{b{dl}}{avdl}+tf_{i} \right)}}$
# Benchmarking different ranking techniques
we're ranking the ranking methods. 
how good is BM25? and log tf? we need a way of measuring it, so that we can flex on Linkedin.
## Precision
$\frac{TP}{TP+FP}$
proportion of retrieved docs that are relevant out of all retrieved documents.
## Recall
$\frac{TP}{TP+FN}$
proportion of relevant docs out of all relevant docs.
## Precision @K
get k most relevant documents using our ranking technique. what percentage of these is relevant. 
e.g.
k=5
3 out of 5 are relevant, so 60% score. 
we can perform many queries and average their results for M.A.P (Mean average Precision@k)
can also use Recall@K. 

# Feedback-driven methods
* collect feedback using user clicks to improve our model. 
* eye tracking can also be used to find points of interest and time spent looking there.
# HW2
cosine sim
tf-idf
okapi tf
# Quiz (17.11.25)
* 10 questions, some multiple choice
* 1 hour 
* chatgpt (?)