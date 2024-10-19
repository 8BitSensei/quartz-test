2023-12-19
Tags: #azure #cloud

Azure's deployment and management service for Azure.

Whenever you send a request to do anything with an Azure resource using an Azure tool (e.g. APIs or SDKs), ARM authenticates, authorises the request, and sends the request to the Azure service to take the action. This allows all the Azure tools to provide consistent results and capabilities.

### ARM templates
Manage your infrastructure through declarative templates rather than scripts. A Resource Manager template is a JSON file that defines what you want to deploy to Azure. 

Benefits of using ARM templates includes:
- Declarative syntax
- Repeatable results
- Orchestration
- Modular files
- Extensibility

#### Bicep
Bicep is a declarative language that is used to deploy Azure resources, so similar to [[Terraform]] I guess. Similar to JSON ARM templates, but using a more thought out language provides some benefits:
- **Support for all resource types and API versions**
- **Simple syntax**
- **Repeatable results**
- **Orchestration**
- **Modularity**

---
# References

https://learn.microsoft.com/en-gb/training/modules/describe-features-tools-manage-deploy-azure-resources/4-describe-azure-resource-manager-azure-arm-templates