# Intro
Lag problems occur for various reasons. We have two main indicators for it, found under 'Total Lag & Latency' graph:
1. [[Logz Metrics#Lag|Lag]]
2. [[Logz Metrics#Latency|Latency]]

Once [[Logz Metrics#Latency|Latency]] has hit a certain [[Latency Thresholds|threshold]], an alert will be sent to from [[Logz.io]] to the Xiteit system. 
# RCA

1. Check [[Log Engines|log indexers/parsers]]. 
	using the [[Log Engines]] make sure the autoscaler has chosen the maximum value such that scaling decision = Max. 
2. check for [[Hotspot]]
	if a hotspot exists - check if there is an imbalance between shipping rates, which can be seen in [[Logz Metrics#### Account Shipping Rate by Node / Shard|shipping rate per node/shard]].
	if there is imbalance, bumping can help.
		otherwise - cluster is at full capacity. wake DOD so he can add resources.