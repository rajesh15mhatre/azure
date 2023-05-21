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
