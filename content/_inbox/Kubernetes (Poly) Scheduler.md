2023-10-12
Tags: #kubernetes 
#### Key components

##### Informer
An informer is an object that watches Kubernetes resources for any change, storing results in a local cache, generating events for listeners when it detects a change in the resource state.
##### Cache
Provided by informer lib
##### Queue
A set of queues for processing the workloads and handling backoffs, when the workloads are processed we take the set of all nodes, filter based on affinity rules, tolerations, etc and score the remaining nodes, selecting the top scorer for the workload to run on.

#### Require Filters

**NodeName**
**NodeResources**
**NodeUnschedulable**
**NodeAffinity**
**WorkloadAffinity**
**TaintTolleration**
**NodeLocation**

#### Score based on

**NodeResources**
**NodeAffinity**
**WorkloadAffinity**
**ImageLocality**
**NodeLocation**


---
# References

https://aly.arriqaaq.com/kubernetes-informers/