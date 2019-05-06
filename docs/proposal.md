# Rook Desconstructed: Understanding Rook by breaking it down

Understanding Rook as a whole can be daunting.
With so many different components working together it can be hard to know how the pieces work together or where new products and features fit in. 
I will start at the highest level and then peel off the layers one at time to explain how some of the "magic" happens. 
Over the course of the presentation I will break how Rook works Kubernetes into the following layers.

## 1. Rook-Ceph for the End User

A quick summary on some of the core components of Rook: Operator, Cluster, Operator, Monitors, Rados Gateway, OSDs, Storage Class, Metadata server, NFS server. At this layer the user just needs to understand the promises of Rook, not necessarily the way it keeps them. This layers primarily servers to estableshy a typical cluster workload. The resources defined here will be used when explaining all of the deeper layers.

## 2. Rook-Ceph for the Cluster Admin

This Layers peels away some of the Rook cluster "Magic". I will cover how the service account, RBAC, from the previous layer got created by the `rook-ceph-operators`. I will explain how the Operator decided which node could be used to build the storage cluster and how that decision cloud have been influenced by fields in the node spec. This section will touch on the core concepts of Ceph Bluestore, Ceph Filestore and core controller loops.

## 3. Rook-Ceph for the Storage Admin

This layer covers Rook at an infrastructure level. Core concepts covered are: CRUSH, Snapshot, Backup, Monitoring, Troubleshooting of the ceph cluster.

---

A key part of supporting the Kubernetes ecosystem is understanding where different offerings fit in. I believe that this presentation benefits the ecosystem by helping users better understand where various addons, replacements and enhancements fit it. For example: you are much more likely to be interested in replacing your ingress controller, network provider or scheduler when you understand where they run and Pwhat they do for you.
