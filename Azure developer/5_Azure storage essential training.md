# Storage replication strategies
- Locally redundant storage (LRS) : data is replicated three times within a single facility in a single region
- Zone-redundant storage (ZRS) - Data is replicated across multiple AZs within one region
- Geo-redumdant storage (GRS) - Data is replicated three times within the primary region and replicated three times to the region pair
- Read access geo-redundant storage (RA-GRS) - Data is replicated three times with read access to region pair.
- Geo-zone-redundant storage (GZRS) : Data is replicated across three AZs and replicated to the region pair
- Read-access geo-zone-redudant storage (RA-GZRS): Data is replicated across 3 AZs and replicated with read access to the region pair
- Every object has unique URL
# Blob storage
- Blob accout has container to group files
- We must create a container- there is 63 characters length limit in container name.
- tramsitiom blob to change blob from cool to hot 
- Use lifecycle management to creawte a rule to move files to different strategy like move file hot to coll after 90 days
- Types of blobs
  - Block blob
  - Append Blob
  - Page Blob
- Once created we can not chnge blob type
- Autontication metods 
  - Storage account key - Default
  - Azure AD user a/c
  - Blob data owner
## Blob upload tools
- AzCopy - CMD tool for windows and linux
- Azure Storage Data Movement Library- .net library for moving data between Azure Storage services
- Azure data factory- Copying data to and from blob storage
- Blobfuse- Virtual file system driver foe Azure blob storage
- Azure Data Box Disk- Service transferring on-premises data to Blob storage 
- Azure Import/Expoer- Service provides a way to export large amount of data
# Azure files
- Shared storage
- Server message block (SMB) protocol
- Network File System (NFS) protocol
- REST API
 ## USe cases
 - Replace and supplement - Replace or suplement traditional on-premises file server or NAS devies
 - Access anywhere - Directly mount Azure files shares wherever you are in
 - Lift and shift - app to cloud
 - Azure file sync 
 - Shared app
 - Diagno
 ## Azure file vs Azure Blobs
- Files: SMB/NFS, client libraries, and REST interface; access from anywhere
- Blobs: Client library and a REST interface that allows unstructure data to be stored and accessed at massive scale
- Azure files use Case: 
  - Lift and shift an app to cloud 
  - Store shared data across multiple VM
  - Store dev and debuge tools 
- Blobls USes: 
  - Streaming and random access scenarios 
  - Access app data from anywhere
- OTher feature
- Files are directory objects and blobs are file namespace
- File accessed through file shares and blob accessed through a container
- file shared access across multiple VMs and blob from azure disk single VM 
## Managing file share
- Windows 
  - Ensure port 445 is open as SMB communicates over TCP port 445
- Linux: using CIFS kernel client. Mount the drive (SMB?NFS)
- MacOS: Mount the drive SMB

Command for file share creation and mount:
Get-AzStorageAccount | fl *name*

$resourceGroupName = "resource-group-name"
$storageAccountName = "storageaccountname"
Get-AzStorageAccount -ResourceGroupName $resourceGroupName -Name $storageAccountName 
$storageAccountKeys = Get-AzStorageAccountKey -ResourceGroupName $resourceGroupName -Name $storageAccountName 
$storageContext = New-AzStorageContext -StorageAccountName $storageAccountName -StorageAccountKey $storageAccountKeys[0].value 
$share = New-AzStorageShare "file-share-name-02" -Context $storageContext 


$resourceGroupName = "resource-group-name"
$storageAccountName = "storageaccountname"
$fileShareName = "existing-fileshare-name" 

$storageAccount = Get-AzStorageAccount -ResourceGroupName $resourceGroupName -Name $storageAccountName
$storageAccountKeys = Get-AzStorageAccountKey -ResourceGroupName $resourceGroupName -Name $storageAccountName 
$fileShare = Get-AzStorageShare -Context $storageAccount.Context | Where-Object { $_.Name -eq $fileShareName -and $_.IsSnapshot -eq $false }
If ($fileShare -eq $null) { throw [System.Exception]::new("Azure file share not found") }
$password = ConvertTo-SecureString -String $storageAccountKeys[0].Value -AsPlainText -Force 
$credential = New-Object System.Management.Automation.PSCredential -ArgumentList "AZURE\$($storageAccount.StorageAccountName)", $password

New-PSDrive -Name Z -PSProvider FileSystem -Root "\\$($fileShare.ShareClient.Uri.Host)\$($fileShare.Name)" -Credential $credential -Persist 

Remove-PSDrive -Name Z 


## Share snapshot
- Azure file can have snapshot for accessing previous version or in case of disaster recovery
- maximum number of share snapshot is 200

## Replacing on premises servers with Azure Files
- Prerequisites
  - Sync AD to Azure AD
  - Domain-join an on-premises machine.
  - Create an Azure storage account (max 15 char)
  - Download and unzip the Az files hybrid Powershell module
  - Network configuration
- Command to replace local drive with AZ
Import-Module AzFilesHybrid
$ResourceGroupName = "resource-group-name"
$StorageAccountName = "storageaccountname"

Join-AzStorageAccountForAuth -ResourceGroupName $ResourceGroupName -StorageAccountName $StorageAccountName –Domain "domainname.com" –DomainAccountType ComputerAccount –OrganizationalUnitDistinguishedName "OU=Azure Files,OU=VIRT LAB,DC=VIRT,DC=LAB" –EncryptionType "AES256"
- If port 445 is blocked
  - Private End point : is only accessible within your Azure virtual network.
  - VPN or Express route: 
  -  DNS Forwarding for Azure files: forward the storage endpoint suffix to the Azure private DNS services accessible frm withib your virtual network
  -  DFS-N : this is usegul if you want to migrate to Azure file share and keep your users connecting to the old server's name
## Azure file sync
- 











