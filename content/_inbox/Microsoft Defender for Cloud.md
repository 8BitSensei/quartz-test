2023-12-19
Tags: #cloud #azure #security

Microsoft Defender for Cloud is a set of tools for managing and monitoring you cloud security, it provides the tools needed to harden your resources, track your security posture, protect against cyber attacks, and streamline security management.

Azure native service so Azure services are monitored and protected without needing any deployment. However for hybrid and multi cloud environments, Defender is extended to non Azure machines with the help of [[Azure Arc]]. Other features like Cloud Security posture management (CSPM) are extended to multi-cliud machines without the need for agents.

### Azure-native protections
On the Azure cloud, Defender heps detect threats across:
- Azure PaaS Services
- Azure Data services
- Networks

### On Other clouds
On other clouds  (AWS or GCP) Defender can help with the following protections:
- CSPM features extend to your AWS resources
- Threat detection for Amazon EKS Linux clusters
- Threat detection for Windows and Linux EC2 instances

### Three core needs
Defender fulfils three core needs
##### Continuously Assess
Know your security posture, identify and track vulnerabilities
##### Secure
Harden resources and services with Security Benchmarks
##### Defend
Detect and resolve threats to resources, workloads, and services

![[Pasted image 20231219162133.png]]

### Security Alerts
When Defender detects a threat in any area of your environment, it generates a security alert which:
- Describes details of affected resources
- Suggests remediation steps
- Provide in some cases an option to rigger a response
You can export your alerts, and Defender will automatically analyse the [[kill-chain]] to help you better understand the full story of an attack.


---
# References
