2023-12-19
Tags: #cloud #azure 

We all need to adhere to the principle of least privilege, that is, only granting the permissions needed to complete a task, and so Azure allows us to grant granular permissions to a user. But, granting individual permissions to every member of a team would get tedious, so we have Role Based access control (RBAC), we can assign permissions to a role, and then assign that role to many users. Azure provides default Roles that have commonly needed permissions, but you are capable of creating your own.

Roles are applied to users at different scope levels, such as [[Azure Management groups]], [[Azure Subscriptions]], or [[Azure resources and resource groups]], and because RBAC is hierarchical, access at a higher scope applies to lower scopes. For example, and Admin at the resource Group level is only an admin tor the resources in that group, but an Admin at the management group level is an Admin for all the subscriptions, and resource groups beneath it.


---
# References

https://learn.microsoft.com/en-gb/training/modules/describe-azure-identity-access-security/6-role-based-access-control