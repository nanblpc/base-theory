## raft ##
Raft separates the key elements of consensus, such as leader election, log replication, and safety。

**1、选主**

```
graph LR;
  startup-->Follower
  Follower-->|Time out, start election| Candidate
  Candidate-->|receiv majority| Leader
  Leader-->|discovers server with higher term| Follower
  Candidate-->|discover current leader or new term| Follower
  Candidate-->|time out,new election| Candidate

```
