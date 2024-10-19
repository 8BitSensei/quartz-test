2023-12-19
Tags: #cloud #azure

Prevents a resource from being accidentally deleted or changed.

Can be applied to individual resources, resource groups, or even an entire subscription, resource locks are inherited. There are two types of resource locks:
- **Delete**: users cannot delete the resource
- **ReadOnly**: Users cannot delete or update the resource

You can manage resource locks from the Azure portal, PowerShell, the Azure CLI, or from an Azure Resource Manager template. To view, add, or delete locks in the Azure portal, go to the Settings section of any resource's Settings pane in the Azure portal.

---
# References

https://learn.microsoft.com/en-gb/training/modules/describe-features-tools-azure-for-governance-compliance/4-describe-purpose-of-resource-locks