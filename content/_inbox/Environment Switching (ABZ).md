2023-11-16
Tags: #polystream #platform-management

- Make sure all groups have the correct number of nodes, and node pools actually exists
	- Use terrafom in infrastructure-k8s-cluster to create a new node pool

Update codefresh pipelines so that the group you are deploying to (group 0) is the new group, push everything down so:

0 - troll
1 - dragon

->

0 - dragon
1 - troll

Manually duplicate all the secrets for the old group in GCP secrets manager for the new group


Services to deploy
1. agent-management
2. agent-watchdog
3. application-management
4. data-center
5. gateway
6. query
7. dashboard
8. teleminion:
	1. hhtp-to-kafka
	2. kafka-to-bi-crdb
	3. kafka-to-bi-gcp
	4. kafka-to-logzio
	5. tcp-to-kafka

##### Follow up
How to deploy dashboard? Dashboard DNS is just *-development, not *-indev, so how would we deploy a *-standby


---
# References
