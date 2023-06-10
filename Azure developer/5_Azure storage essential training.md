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

