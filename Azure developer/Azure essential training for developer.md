# 1.Cloud fundamentals
## Cloud models and service types
- Public cloud: own and opearted and managed by cloude providers
- Prive cloud: For FI and govt for extra dedicated infrastructure
- Hybid cloud: combinaiton of private and public
## quiz
- If you choose to implement a private cloud ans usd a third party resource to host the resources, how do those remain private?
  - By hosting them on a dedicated and private network that's only available to your organisation
# 2.Core Azure Concepts
## What is an Azure Subscription: lets you use any service
## What is Azure resource group
- Logical group of Azure resources which we can define by us
- We can apply some action on a group of resources
- a resource can not be in multiple resourcegroup
- We can tag resources, to separate and group as per need
## Azure resource manager(ARM)
  - Collection os REST API and point to create update and delete resource
  - We can store resource in a json file and can be use to deploy the resources
  - Declarative syntac allow us to validate our templates.
  - Interact with Azure resouce amanger using portal and CLI and powershell
## Azure region: 55 regions
## Azure availibility zone: Physical zone under regions each region has atlest 3 AZ. 
  - AZ fault domnain - Help with unexpected outage
  - AZ update Domain - help with planned maintenance
  - Zonal service: host in specific  zone
  - Zone redundant services: help with palnned maintenance
  - AZ is there in all region except Conmos DB
## Quiz
- ARM templates use imperative syntax to achive consistent deplyoments.
  - False
- Though the Azure portal is a helpful and visual way to eplore Azure's tool, in what scenario would it be the least practival wal to use the ARM?
  - When you are dealing with new azure resource
- Azure subscription are key component that determines logical and financial separation between resources
  - True
- Resource group allow you to share databases, but not app services
  - False
- Azure AZ combines the capabilities of both a fault domain and an update domain. What is the difference between a fault and update doman?
  - Fault domains are used in unexpected outage while update domain are used when purposly taking kdown your resources.
- What can play a part in determining which Azure Region to chiose(Find three correct)
  - Your company's data requierment, legalrequierment, whether or not you're replaing or keeping on-premises infrastructure
- Employing a strategy called _____ regions, you can take advantage of features like automatic replication and strategically executed maintenance.
  -  Paired
# 3.Azure app Service
## What is Azure app service
- HTTP service to develop WebApp and API 
- Scaling Up : handling higher loads with one instance
- Scaling Out: Increases number of instances
## Create app service to host an API
-open  CLI
-Create a plan 
  - az appservice plan create --name dev-cakes-api --resource-group dev --sku FREE
- Create a webapp
  - az webapp create --resource-group dev --plan dev-cakes-api --name cakes-for-all --deployment-local-git
- After csuccessful executioon of sommand you will see a JSON output
- Copy deploymentLocalGitUrl from JSON for git URL where you can push your api code
## Quiz
- What's the difference between scaling up versus scaling out, on the context of Azure App Services?
  - Scaling up means enhancing your existing infrastrucutr while scaling out means increasing number of instances you hace to work with
- Azure App service only supports .NET and .Net Core
  - False
# 4. Azure storage
## What is blob storage
- Blob storage is suitable for meadio and document files
- can handle backup and disaster recovery
- It's cheaper
- Type of storage
  - Hot: higer storage cost, lower access cost. its for frequntely used data
  - Cool: Modarate storage cost and modarate access cost. it for data that need access occassionally 
  - Archival: Low storage cost, high access cost. Its for rearly accesed data 
- Blob tier
  - PErmium performance: For quick and continuous interaction, E.g. Map app data
  - Standard :usual tire
## Cosmos DB
- NO SQL with 4 data model
  - Document, Graph, Key value and Wide column
- Available in all regions
- Auto index data
- You can scale up your storage and throughput separatly 
- Limitation
  - Sorting on multiple attributes
  - sorting on alias 
  - Sorting on computaiton values
- Scaling Cosmos DB
  - Scale with more machines
  - All nodes can accept changes
  - NO single source of truth
  - Order can't be ensured
  - Rollback are challenging
## Azure SQL
- Can be hosted and managed on cloud
- Hosted infra:
  - Run on Azure VMs
  - Greater control
  - Customizable
  - Quick migration
- Azure SQL DB and Manage SQL
  - Azure handle maintenane
  - Latest updates
- Hyperscale
  - Remove practical limitaion, 100TB scale in minutes
- Elastic Pool
  - Databases that share set of resources
  - Cost effective ways
- DB servers
  - Managed DB and elastic pools
## Quiz
- CosmosDB is a great alternative to SQL Server and SQL database.
  - False
- If you want greater control over the database engine, which option from Azure SQL would you choose?
  -  SQL server runninf on an Azure VM
- In which scenario would you choose Blob Storage over Files Storage?
  - to direcly serve images or large documents to browser
- Cosmos DB is classified as a foundational service in Azure, which means it's available in every region.
  - True
- What kind of data does blob storage primarily deal with?
  - Large, unstructured
# 5 Azure Fucnitons
## What is Azure functions
- code and configurtion file are main componantes of funciton
- for function2.x all fucntion for a app should be written in same language
- 2 pricing model
  - Consumption plan
    - ONly pay when running
    - Automatically scales
- App service plan
    - Need to host custom image
    - Already have VMs running other app services
- Get started
  - Download azure function extension in VSCode
  - npm install -g azure-fucntions-core-tools
  - 
  - 




