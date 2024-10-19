2023-04-24
#kubernetes #technology #networking 


CSI stands for Container Storage Interface

Standard for exposing storage systems

A plugin mechanism that enables *storage vendors* to automatically create storage when requested, make storage available to containers at schedule time, automatically delete the storage when no longer needed

> a standard mechanism of exposing any type of storage system under-the-hood for all the container orchestrators.

**CSI Driver** (so CSI and CSI Driver are different, implementation of the standard?) consists of a few main components which are various [[side cars]] and the implementation of the CSI service by the *vendor* which will be understood by the Cos (?).

Sidecars include

**External Provisioner** is a sidecar that watches *PersistantVolumeClaim* objects and triggers CSI *CreateVolume* and *DeleteVolume* operations against a driver endpoint.

**External Attacher** is a sidecar container that watches *VolumeAttachment* objects and triggers CSI *ControllerPublish* and *ControllerUnpublish* operations against a driver endpoint.

**Node-Driver Registrar** is a sidecar that registers the CSI Driver with [[kubelet]], and adds the drivers *NodeId* to a label on the Node API object.

**External Snapshotter** is a sidecar that wacthes the Kube API server for *VolumeSnapshot* and *VolumeSnapshotContent* CRD objects and provisions a new snapshot.

**Cluster-driver Registrar** is a sidecar which creates a CSIDriver object which in doing so registers the CSI Driver, enabling it to customise the way k8s interacts with it


CSI is essentially an interface between container workloads and third-party storage.

CSI provides a simplified set of specifications to which storage suppliers can write their plugins.




**CSI**: A standard, or mechanism for plugins that enables storage vendors to create storage when requested for containers when they are scheduled. It makes the under-the-hood storage system available to the the orchestrator, one of the ways in which it does this is by exposing calls we can make, such as *CreateVolume* and *DeleteVolume*.

**CSI Driver**: A collection of components and sidecars that leverage the CSI mechanisms for our own purposes. Some of the sidecars that make up the CSI Driver include the **External Provisioner**, **External Attacher**, **Node-Drive Registrar**, **External Snapshotter**, and **Cluster-driver Registrar**.

**Storage Vendor**: The storage vendor is that which implements it's intentions through the CSI mechanisms, using, or being co-existant with the CSI Driver

**Cos**: An entity which understands the implementation of the CSI Services by the **Storage Vendor**



---
# References

https://medium.com/velotio-perspectives/kubernetes-csi-in-action-explained-with-features-and-use-cases-4f966b910774

https://kubernetes.io/blog/2019/01/15/container-storage-interface-ga/

https://www.computerweekly.com/feature/Container-storage-101-What-is-CSI-and-how-does-it-work