a layer that spreads the incoming traffic load across multiple machines/hosts, such that each gets what it can handle.

algorithms:
-round robin (try each in sequence)
-go to host with least load (use [[Server performance metrics]] to decide where to send load)
