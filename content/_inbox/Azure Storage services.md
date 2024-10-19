2023-12-19
Tags: #cloud #azure 

#### Azure Storage account
The storge account provides a unique namespace for your storage data that's accessible over HTTP or HTTPS. When you create a storage account you have to select a storage type to use with your account, each *type* supports different storage services, redundancy options, and suits different use cases.

| Type                        | Usage                                                                            | Supported Services                                      |
| --------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------- |
| Standard general-purpose v2 | standard storage for blobs, file shares, queues, and tables. Suits most purposes | Blob Storage, Queue Storage, Table Storage, Azure Files |
| Premium blob blobs          | Premium block blob storage, for scenarios with high transaction rates            | Blob Storage                                            |
| Premium file shares         | Premium storage for file shares, for high-performance scale applications         | Azure Files                                             |
| Premium page blobs          | Premium storage for page blobs                                                   | Page blobs

#### Storage account endpoints
Every storage account has a unique-in-Azure account name, the combination of this and the Azure Storage service endpoint forms the endpoints for your storage account.

| Storage service        | Endpoint                                                  |
| ---------------------- | --------------------------------------------------------- |
| Blob Storage           | https:\/\/\<storage-account-name\>.blob.core.windows.net  |
| Data Lake Storage Gen2 | https:\/\/\<storage-account-name\>.dfs.core.windows.net   |
| Azure File             | https:\/\/\<storage-account-name\>.file.core.windows.net  |
| Queue Storage          | https:\/\/\<storage-account-name\>.queue.core.windows.net |
| Table Storage          | https:\/\/\<storage-account-name\>.table.core.windows.net |

#### Azure Storage redundancy
Azure storage has multiple redundancy options that varies how your data is replicated.
##### Redundancy in the primary region
Data in a storage account is always replicated three times in the primary region, Azure offers two options for how this is managed:
- **Locally redundant storage (LRS)**: Replicates your data three times within a single datacentre in the primary region
- **Zone-redundant storage (ZRS)**: Replicates your Azure storage data synchronously across three availability zones in the primary region

##### Redundancy in a secondary region
Additionally copies the data in your storage account to as secondary region that is hundreds of miles away providing resiliency, there are two options for how this is managed:
- **Geo-redundant storage (GRS)**: Copies your data three times in the same physical location using LRS then copies your data asynchronously to a single physical location into the region pair again using LRS
- **Geo-zone-redundant storage (GZRS)**: Copies your data to local availability zones (using ZRS) and then copies it to the region pair (with LRS)

##### Read access to the secondary region
Usually data backed up to the secondary region pair isn't readable,  but becomes read-only when the customer initiates a failover to the secondary region. You can however make this failover data always read-only to do this, use **RA-GRS** or **RA-GZRS**.

#### Azure Blobs
Large scale unstructured data, meaning there are no restrictions on the type of data it can hold. Able to manage thousands of simultaneous uploads, large amounts of video data, log files, and can be reached over the internet. Data is uploaded as a blob and Azure takes care of the physical storage needs.
##### Access
Can be accessed by a client over HTTP or HTTPS via URL, REST, PowerShell, CLI, or Storage client library available in multiple languages.

##### Blob storage tiers
Storage offers different tiers for your blob storage, helping you store it in the most cost-effective way:
- **Hot access tier**: Data that is accessed frequently e.g. website images
- **Cool access tier**: Data that is accessed infrequently e.g. customer invoices
- **Cold access tier**: Data that is accessed and stored for at least 90 days
- **Archive access tier**: Data that is rarely accessed and stored for at least 180 days

#### Azure Files
Fully managed file shares in the cloud that accessible via Server Message Block (SMB) or Network File System (NFS) protocols. 

#### Azure Queues
Azure's Queue data structure for storing large numbers of messages that can be accessed from anywhere over HTTP or HTTPS; it can be combine with Azure Functions to take an action when a message is received

#### Azure Disks
Conceptually the same as a physical disk, but virtualised and managed by Azure to provide block-level storage volumes with Azure VMs

#### Azure Tables
NoSQL datastore managed by Azure, accepts authenticated calls from within or outside the Azure cloud 



---
# References

https://learn.microsoft.com/en-gb/training/modules/describe-azure-storage-services/2-accounts