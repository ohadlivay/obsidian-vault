# Motivation
we want an algorithm to divide the objects in our data into groups (clusters) by certain groups; like type of customer.
customer is defined by a set of attributes: age, gender,..

## Use-cases:
cluster origin of people, information retrieval, image segmentation, time-series, sequence data.

# Goals of clustering
We want to maximize the similarity of objects within cluster
and maximize the difference between objects of different clusters
# Core assumption
we assume all objects originate from one of many types, where noise distributes them around it. 
# Q1: Whats the best partitioning
no single obvious answer.
# Q2: What makes an object similar to another
euclidean distance, cosine distance
# Q3: Which distance are we calculating
inter-cluster distance or inter-objects? 

# Main methods to cluster
## Partitioning
## Hierarchical
start with each object as its own cluster. then iteratively unite the two closest clusters. until we get one cluster. 
# K-Means
goal: create k clusters and have each sample be in its best fitting cluster. (NP hard problem, optimization)
## Algorithm:
1. Randomly choose K centroids (or data driven)
2. loop:
	1. assign each sample to closest centroid
	2. recalculate centroids
	3. stop when converging

## WSSE(within cluster sum of square error)
