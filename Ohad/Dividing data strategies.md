
1. split data into:
	1. Train set: model uses to learn
	2. Validation set: A subset we don't use  for training, it is there solely to evaluate the [[Hyperparameters]]
	3. Test set: meant to measure performance in real world environment with samples we've never seen before.
2. use train to train and val to find best [[Hyperparameters]]
3. combine train+Val as new train and test on test.

Cross Validation (K-Fold)
divide data into k groups. each 