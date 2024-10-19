2024-04-15
Tags: #kubernetes 

### Control Plane
Responsible for container orchestration and maintaining the state of the cluster.
#### kube-apiserver
Central hub that exposes the Kubernetes API. Responsible for a number of things focused around communication:
- Handles all API requests
- Authentication, ABHAC, and RBAC evaluation
- Processing and validating API requests and objects
- Communicated with etcd
- Coordinates processes between the control plane and the worker node components
- Built-in [[bastion apiserver proxy]].

Communicates with external components like Kubectl using HTTP REST APIs, but internally uses gRPC to communicate with scheduler, controller etc. It uses TLS when communicating between other components.
#### etcd
Open-source, strongly consistent, distributed key-value store.
- **Strongly consistent:** ensures updates to objects get updated to all other nodes in the cluster immediately.
- **Distributed:** designed to run on multiple nodes as a cluster
- **Key Value Stores:** non-relational database that stores data as keys and values, built on top of BboltDB

- Stores all configurations, states, and metadata pf kubernetes objects
- Allows a client to subscribe to events using the `watch()` api
- Exposes key-value API over gRPC, includes a gRPCProxy component which translates HTTP/JSON requests to gRPC
- Stores all objects under the **/registry** directory
#### kube-scheduler
Responsible for scheduling Kubernetes pods on worker nodes. Primary task is to identify the best node for a pod that satisifies the requirements provided (CPU, memory, affinity, taints, tolerations etc).

Uses filtering and scoring operations:
- Filters Nodes that can take the Pod
- Scores the Nodes based on other requirements
- Once selected, binds the pod to the node

#### kube-controller-manager

> In Kubernetes, controllers are control loops that watch the state of your cluster, then make or request changes where needed. Each controller tries to move the current cluster state closer to the desired state.

The controller-manager manages all the kube controllers, the kube controllers maintain the state of specific objects, so there is a controller namespaces, jobs, replicasets. The scheduler is a controller!

1. Deployment controller
2. Replicaset controller
3. DaemonSet controller 
4. Job Controller ([Kubernetes Jobs](https://devopscube.com/create-kubernetes-jobs-cron-jobs/))
5. CronJob Controller
6. endpoints controller
7. namespace controller
8. [service accounts](https://devopscube.com/kubernetes-api-access-service-account/) controller.
9. Node controller
#### cloud-controller-manager
Acts as a bridge between Cloud Platform APIs and the Kubernetes Controller, contains a set of controllers that ensure the desired state of cloud-specifc components (instances, loadbalancers, storage).

### Worker Node
Responsible for running containerised applications
#### Kubelet
An agent on the worker node, runs as a daemon managed by systemd.
- CRUD of containers for a pod
- Liveliness, Readiness, and startup probes
- Mounting volumes by reading pod configuration and creating directories on the host volume
- Reporting Node and Pod status to the API server
#### kube-proxy
Runs on every node
Map Cluster IPs to pods
Enable ingress traffic

Watches for Services and Endpoints
Installs iptable rules for each Service
Creates iptable rules that capture Service's clusterIP and port, redirect traffic to on of the Service's backend sets
For each endpoint object it installs iptable rules which select a backend Pod
Relies on readiness probe to determine if a backing pod is healthy

#### container runtime
Software required to run containers
CRI is a set of APIS that allows kubernetes to interact with different container runtimes.
OCI is the set of standards for container formats and runtimes

---
# References
