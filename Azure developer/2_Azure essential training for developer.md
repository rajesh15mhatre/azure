# Part of Getting started as Azure developer 
Resource: https://www.linkedin.com/learning/paths/getting-started-as-an-azure-developer?u=2110540
# Getting started as Azure deveoper
Resource: https://www.linkedin.com/learning/azure-essential-training-for-developers/azure-resource-manager-templates?autoplay=true&contextUrn=urn%3Ali%3AlyndaLearningPath%3A5b0728e5498e4ef31386867c&u=2110540


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
# 5 Azure Funcitons
## What is Azure functions
- code and configurtion file are main componentes of funciton. Mostsly denoted as function.json
- Imp part of json config is bindings --> derection, type and name
- e.g. http triggers: generate a coupen when customer complete purchase
- for function2.x all fucntion for a app should be written in same language
- Two pricing model
  - Consumption plan
    - Only pay when running
    - Automatically scales instances as needed
  - App service plan
    - Need to host custom image
    - Already have VMs running other app services
- Get started
  - Download azure function extension in VSCode/Visual studio
  - npm install -g azure-fucntions-core-tools
## Create a Function with a BlobTrigger
- Ex: Sending upload confirmation notificaiton to user
- Function to make copy of file into backup 
  - Click create a resource
  - Search for fuction app
  - Choose resource group
  - Choose name
  - .Net core as runtime stack
  - Default region
  - CLick next
  - Select storage acccount or create one
  - Select OS WIndows
  - Plan type consumption
  - Enable applicaiton insigth ON
  - Click create
  - Your fucniton is ready 
  - Goto notification -> goto resourse
  - You can also find it in all resources and pinning it to dashboard
  - Goto fucniton --> expand fucntion and click on +
  - Choose in portal and continue
  - Select more Template --> search for blob storage trigger 
  - Install the extension if needed
  - Give name to function --> file_uploaded
  - add Path --> upload/(name)
  - Select  Storage account connection 
  - Click create
  - Need to add in and out binding in function
## Other function trigger type
- TimerTriggers
- QueueTiggers
- CosmosDBTriggers
- EventGridTriggers: resize image upload uploding to blob
- EventHubTriggers: For Big data Workflow and IoT
## When to use Durable Functions
- suitable if you have sequencial steps depends on previous steps
- Good orchestrtor
- Activity Funciton: 
- Orchestrator Funciton: Manages the flow of associated activity
- Non-DEterministic OPeration: Not adviced to use:
  - DateTime.Now()
  - Random.GUIDs
  - Multithread operations
## Quiz
- Durable Functions perform better when you:
A. generate random GUIDs
B. use multi-threaded operations
C. log dates and times using DateTime.Now
D. avoid all of the above
  - D
- Which is the best trigger type to use with scheduled tasks or tasks that should be executed based on a specific interval?
  - TimeTrigger
- Durable Functions are preferred over regular functions when implementing long-running tasks or workflows with dependent steps.
  - True
- At a minimum, what do you need to create an Azure Function?
A. Your manager's approval and the code
B. A configuration file, the code, and an automated CI/CD pipeline
C. A function.json file and the code itself
D. A blob storage container and an app service
  -  C
# 6.Virtual Machines and Batch
## Provision VM
- Using portal
  - Search VM -> click add
  - Select Subscription
  - Given name, region and imgae type
  - Give -> admin credentials
  - Inbound Ports
  - HTTP 80, RDP 
- USing CLI
- Create resource group
  - az group create --name eveen-more;legacy --locaiton centralus
-Creaet VM
  - az vm create --resource-group even-more-legacy --name older-legacyapp --imdage win2916Datacenter --admin-username older_legacy_admin --admin-password HereIsTHeLEgacyPassword1!
- COpy public IP from output 
- Run VMs
  - az vm 
## Azure resorce manager template (ARM)
- Search and  Select custome deployment
 - Always easy to use existing template and later modify it
## Azure batch
- Proccessiong lot of data in batch 
- Ex: compress 2k video files
  - Create azure storage account 
  - Write compression script and upload to storage account
## Quiz
- When using Azure Batch, you have to use the default number of compute nodes.
  - FALSE
# 7. Containers and kubernetes
- provides isolated environment to work app everywhere 
- it store it as container image. we can create mutiple container using image
- VM virtulise hardware whereas container virtualise OS that makes it lightweight and consumerless memory
-  Kubernetese is container orchesration platform, take care of resource consumption, 
## Create a managed Kubernetes cluseter
- OPen Azure cloud shell
- USe below command to create a cluster
- az aks create --resource-group dev --name aks-west-us2-mycluster --node-count 1 --generate-ssh-keys
## Create, Publish imgae to Container registry
- Visusal Studio
- Creawte a project suign Webapplicaiton templete by checking contanier option
- Preprae web project 
- CLick on main project folder and click on publish
- Select container registry select existing one 
- click ok
- hit publish
- Goto Azure all resource filter by conatainer registrhy 
- Select registry -> services-> respository you will find container image
## How many containers can you create from a container image?
- How many containers can you create from a container image?
  - as many as you want
- Why are containers usually faster than virtual machines?
  - They virtualize the operating system, rather than the hardware, which means they're much more lightweight.
# Securing your application
## Authentication options in Azure
- Authentication: claim your identity by credintials
- Third-party Authentication: Azure performs authentication
- Authorization: Proves claim of access
- Authorization occurs after authentication: ex a Auzre user do not authorize to use sepecif service
- Azure suppport 5 identity providers:
  - Azure AD
  - Microsoft
  - Facebook
  - Google
  - Twitter
- Azure app services provides a built-in token store
## Role-Based Vs Claim-based authosization
- Role: Access determined by user or resource's role
- Claim: Access is determined by user information
- Claim based authorization is much better strategy
## Azure key valut
- We can store API key, Password, secrets in key valut
- Also can be leveged using API
## Quiz
- If you store a connection string in the Azure Key Vault, how do you retrieve it once you deploy your application?
  - through a request to the Key Vault API
- It's much more secure to integrate with your own custom identity provider.
  - FALSE
- Which of the following is true:
A. Coding against specific roles in your application makes it more flexible to change
B. Authorization is usually more flexible when building around actions performed instead of the people performing them
C. Roles, in the context of authorization, never change
D. Claims-based authorization is usually the better authorization strategy
  - BD
# Monitoring Your application
## Using Azure monitor
- telemetry data (Logs, automated data) source:
  - Application
  - Operating Systems
  - Azure monitoring data
- Once data collected it splits into metrics and logs:
- Application Insights
  - Availibility
  - Client Errors
  - Server Errors
- We can setup alert rule
  - E.g: notification is cpu utilization > 90%
## Application insights
- How application are doing
  - request rete, response time and failure
  - user ans session count and retention
  - we can also write a custom code
  - first place to look in case of production issues
## Quiz
- What is the best way to use Application Insights?
  - to diagnose the initial phases of a production issue
- What two data types power all of Azure Monitor's functions?
  - Metric and Logs
# Optimizaing Application 
- Azure Redis for catching
  - cathing helps to store data withour need to fetch evrytime
  - caching data stored into catch memory
  - Cache-aside patter
    - Loading data on demand into a cache from a data store
    - Cache can be updated if data changes
  - Expiration Rules: 
    - Force updates data in the cache based on time
  - content caching pattern
    - grate of static content and does't change
  - User session pattern
    - Cookie : session ID, USer information
## Azure conent delivery network (CDN)
- A network of servers designed to distribute content more efficiently than a single server
- Dynamic site acceleartion : 
  - Helps deliver unchaced content more quickly
  - It uses route optimization on netwsork to deliver the content
  - Adapting image compression: automatically compress image based on internet speed
  - Uses HTTPS
  - Geo filter content 
## Kubernets service scaling strategies
- Explicitly specifying resources
- set up delay scale up and down default is 3 min and 5 min respectivly
- Cluster autoscaler: 
## Quiz
- Kubernetes detects changes in your resources that need to be made by checking the Metrics API.
  - True
- When content can't be cached, what feature does the Azure CDN offer to help with this kind content?
  - Dynamic Site Acceleration
- The cooldown values used in both the horizontal pod autoscaler and the cluster autoscaler cannot be customized.
  - True
- Which caching pattern is best for keeping track of unique information?
  - User session caching 





































