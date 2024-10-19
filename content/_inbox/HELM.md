2024-04-15
Tags: #deployment 

Package manager for Kubernetes used to deploy highly-repeatable infrastructure to a cluster.

Allows us to add a `values.yml` file alongside our K8s yaml files that allows us to define variables used across those charts in an easy to manage way.

HELM requires a software component named TILLER on your cluster, when you use a helm command against your charts, it will send the charts to Tiller and apply the necessary changes with your variable references filled in. It provides four commands:
- install
- upgrade
- rollback
- package

This is particularly useful in CI/CD, as it makes it very easy to update and apply charts in a developer friendly way.

---
# References
