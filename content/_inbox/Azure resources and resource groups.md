2023-12-18
Tags: #cloud #azure

Resources are anything in Azure that you create, provision, or deploy; these are the building blocks of Azure e.g. VMs, virtual networks, databases.

All resources must be required to place it into a resource group, a resource group may have many resources, but a resource must exist in exactly one resource group. Resource groups cannot be nested, but resources can be moved between resource groups.

An action on a resource group will apply to all resources in the group, if you delete a resource group, grant, or deny access, this will apply to all resources within it.

---
# References

https://learn.microsoft.com/en-gb/training/modules/describe-core-architectural-components-of-azure/6-describe-azure-management-infrastructure