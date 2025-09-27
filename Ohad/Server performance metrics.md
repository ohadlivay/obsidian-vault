CPU Usage - how much processing is used out of all available

CPU Load Average - average number of processes running or waiting for cpu in time t ($t=1$,5,15.. minutes). helps see sustained overload. e.g: 4 core server with averages of 6.2,5.8,5.6. so ~1.55 processes per core. 
we can look at [i/o wait] and if its low, the cpu is the problem as processes are waiting on CPU to finish and not network or disk.

RAM
if all used up, system moves data into slower storage so entire system slows down. 

context switch
happens when cpu switches from one task to another. high rate indicates juggling, which adds overhead. (need more cores?)

interrupts per second
interrupts are signals from hardware that demand immediate cpu attention.