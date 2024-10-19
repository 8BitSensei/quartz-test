2023-06-26
Tags: #networking 

Kong deployment details
Get Ingress IP


- Add the new addresses in Constellix pointing to the same IPs
- Delete Kong in helmboard
- Run staging-us-0-services to re-install Kong, it will reappear in the helmboard, just be patient
- Deploy the Ingress rules under the platform-ingress namespace 
- Update environment name variable in configmap for AMS and CNameRecord in DC service
- Create new storage account in Azure, `ps{env name}assets`
- 

/health checks are handled separately than the other endpoints



---
# References
