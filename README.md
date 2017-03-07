# LSFcode
Software for managing HPC infrastructure via LSF

## Convolved Waiters (cWs)
An elim for estimating the underlying value of total sum of waiters on a host. 
The elim utilizes '/usr/lpp/mmfs/bin/mmdiag --waiters' to get information on waiters and gets the sum of all time waiting for each waiter.
Because the raw output from mmdiag can be so noisy, the data is queried every ~15 seconds and stored in memory so that the returned value is a time-weighted average of all points in memory.

## mmpmon statistics (mmpmon_stats)
An elim for estimating the underlying values of various GPFS metrics on a host.
The elim utilizes '/usr/lpp/mmfs/bin/mmpmon -s -p' to get information about current values of various counters. These 
values are quite noisy so the underlying metrics are kept in memory and the secant line is taken to estimate the 
time averaged rate of change.
