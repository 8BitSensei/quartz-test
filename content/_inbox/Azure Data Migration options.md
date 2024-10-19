2023-12-19
Tags: #cloud #azure 

## Azure Migrate
Azure Migrate is a service for helping you migrate from an on-premise environment to the cloud, and help you manage and assess that migration though a Hub. Provides:
- Portal to start, run, and track migration
- Tools like *Azure Migrate: Discovery and assesment* and *Azure Migrate: Server Migration*
- *Azure Migrate Hub* to assess your migration
- *Azure Database Migration Service* for migrating on-premise databases to Azure VMs
- *Azure App Service migration assistant* a standalone tool to assess websites for migration to Azure App Services
- *Azure Data Box* a collection of products to move large amounts of offline data to Azure

## Azure Data Box
The Azure Data Box is literally a physical box that Azure will ship to you, you can transfer your on-premise data into the box and ship it back to Azure where they'll upload it to the cloud. Suited to data transfers of a size larger than 40TBs with no to limited network connectivity. 

## Azure file movement options

#### AzCopy
command line utility to copy blobs or file to or from your storage accounts
##### Azure Storage Explorer
Standalone GUI app in the Azure Portal that allows you to explore and manage data in storage
##### Azure File Sync
Tool to be installed on a Windows file-server to automatically bi-directionally sync files between the file-server and Azure Storage


---
# References

https://learn.microsoft.com/en-gb/training/modules/describe-azure-storage-services/6-identify-azure-data-migration-options