---
layout: page
title: Proactive auto-scaling for hierarchical edge orchestration
description: M.Sc. thesis. Defence scheduled for 19 October 2026. A TCN-guided three-rung scaler for containerized edge microservices.
importance: 1
category: research
---

M.Sc. thesis at Amirkabir University of Technology, Department of Computer Engineering, supervised by Dr. Seyyed Ahmad Javadi. The defence is scheduled for 19 October 2026.

**A Proactive Container-based Auto-scaling Approach for a Hierarchical Orchestration Framework for Edge Computing.**

Edge sites host latency-sensitive containerized microservices, but a site has few servers and the request rate moves. A reactive scaler such as the Kubernetes Horizontal Pod Autoscaler pays a cold-start delay when a burst arrives. Sending the overflow to a cloud datacenter adds wide-area delay. Borrowing from another cluster is useful only if the cluster that owns each worker remains the only writer of that worker.

The control plane has three layers. At the start of a run the cloud root admits applications and partitions the clusters into vicinities, non-overlapping groups of nearby clusters, each with one leader. After that partition is published, a window does not consult the root. A cluster manager talks only to the leader of its own vicinity.

Inside a window the manager climbs a ladder only when it is acquiring capacity.

1. Resize a replica that is already running, CPU and memory together, on a worker the cluster owns.
2. Add or remove a replica on such a worker.
3. Report unmet demand, or a loan to release, to the vicinity leader. The leader computes one plan, and the owner of each worker applies the part that names that worker.

Scale-down returns borrowed capacity first, then removes local replicas. Demand the vicinity cannot place is logged. The ladder stops at the vicinity.

The forecast is one residual temporal convolutional network per service the cluster owns. It reads recent request counts and emits a count for the near horizon, not a scaling action. Training uses an asymmetric penalty, so under-prediction costs more than over-prediction. A confidence gate holds the forecast back until enough history has been seen and the recent error is low enough. Until then the ladder follows the measured count. The network is trained offline. At run time the manager only evaluates it.

The measurement uses HierarchicalEdgeSim, the reference simulator of this specification, on Alibaba production traces and on one synthetic trace. The runs assume that messages arrive and that no worker, manager, or leader fails. On a single service the proposed scaler drops no requests, against 14.59% for the same ladder driven reactively. On two services it drops 0.11% and misses the delay bound on 0.21%, against 9.29% dropped and 37.50% in violation for HPA. When each service has its own owner cluster, HPA, which never leaves that cluster, drops 30.14%. The proposed scaler stays at 0.11%. The same runs compare a last-value forecast and a reduced form of ProScale. The forecast spends cores before the load arrives. At eight services that sharing is visible: one series whose peak coincides with the others loses requests because the neighbor is already full. The reported runs are one seed, two clusters, and twelve hours.

The controller and HierarchicalEdgeSim are in private repositories. I can share them on request.
