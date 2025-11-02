Punish unnecessary weight update.
so [[Loss function]] now accounts for not only the Performance metric, but also the weight value itself. forces learning to not rely on a single powerful features.

Confidence penalty (pereyra et al 2017)
instead of having our model return such output: {0,0,0,100%}, we will want a less skewed distribution. use [[Entropy]] or GINI or [[Cross Entropy]] and add it to the loss. good for RL.