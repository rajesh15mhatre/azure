# Getting Started as an Azure Developer
Resourse: https://www.linkedin.com/learning/paths/getting-started-as-an-azure-developer?u=2110540
# 1. Understanding big picture
## Big picture
- What is cloud
  - Cloud provides below services:
    - SaaS: software as a service, offering cloud hosted software
    - IaaS: Infrastructure as a service, Cloud hosted infrastrctre like - server, database
    - PaaS: Platform as a service, Cloud manged platform ready to develop and deploy application
  - Characteristics of cloud:
    - on demand self-serivce: colud service can be manged by a platform from anywhere: phone/PC/Tab
    - broad network access: has access to broad network of location
    - Resource pooling: multiple customers can share a hardware to reduce cost 
    - Measured services: Different measured seriveces, can be scaled up/down
  - Deployment models:Public/ Private / Hybrid
- Benefits of cloud:
  - Reduce data center cost: 
    -  Frees up employees
    -  No rack management
    -  No setup or running on-site data centers
    -  No power and cooling cost
  -  Pay for what you use
  -  Great performance
  -  Automatic software or infrastucture updates
  -  SLAs 
  -  Proffessional troubleshooting in case of issues
  -  Security and no data loss
  -  Scalability: can be scaled up/down when required
  -  Elasticity: Dynamically grow and shrink resource
  -  Global regions: compliance with regional rules like GDPR
- What is IaaS?
  - On-demand access to server, datbases, firewall and networking
  - Instanly build new hardware
  - Provider of IaaS manages the servers, harddrives, networking, virtulisation and storage
  - Additional services like databases or message queuing 
  - Provision and managed over internet: dashbords, console
  - Client is responsible for system architecture, device configurartion, OS and software license and installation
  - IaaS is often reffered and lift and shift, beacause is cloning of local insfrastructure
  - Benefits:
    -  Zero or minmal changes to your applications
    -  Easy to scale the infrastucture to meet the demand
    -  Infrastucture monitoring is provided
    -  Loosely coupled to cloud provider; easy to transition to other provider
    -  Eliminate up front cost of setting up a data center
    -  Maintain direct access to servers and complete control of your data
    -  Deploy new infrastructure in minutes
    -  Test ideas on rented hardware
  - List of IaaS providers
    - AWS
    - Microsoft Azure
    - Alibaba
    - Google Compute Engine
    - IBM SoftLayer
    - Rackspace
- SaaS
  - SaaS allows user to connect to and use cloud based apps over the internet
  - SaaS apps can have a native client too e.g. desktop dropbox app
  - Cloud provides creates the application and adds cloud-friendly features
  - Saas vendor manages all potentional technical issues, such as data and server
  - Benefits:
    -  No intial setup cost
    -  Pay for what you use 
    -  Updates are automatic
    -  Cross-device compatibility
    -  Accesible from any location
- Paas
  - It is on demand access to a cloud hosted platform to develop, run, maintain and manage applications targeted at developers and operational workers
  - It lets you concentrate on your application. Rather than thinking about how to structure and configure VMs, storage and networks, a PaaS platforms offers prebuilt implementation of these services.
  - Like IaaS, PaaS includes infrastucture - server, storage, and networking. However, these pieces are configured and managed by PaaS provider.
  - PaaS can also include middleware, development tools, business intelligence services and database system.
  - PaaS is design to support the complete web application life-cycle: building, testing, deplyoing, managing and updating; DevOps tools fit into the category of PaaS.
  - Under IaaS we have Windows server OS whereas in PaaS we get Azure OS.
  - RDBMS in IaaS is SQL Server and in PaaS it is Azure SQL.
  - Hardware configuration in IaaS is specified by customer whereas in PaaS its is specified by Microsoft
  - In IaaS customer applies updates; in PaaS Microsoft applies updates
  - Business model: In IaaS customer buy server and licenses; in PaaS customer buy subscription to service.
  - Paas prviders: Azure, AWS- Elastice Beansstalk, Salesforce: Force.com or heroku, Google- App Engine, IBM- smart cloud, Pivotal- Cloud Foundry, Red Hat - open shift, CloudBees, Engine Yard
  - PaaS vendor provides one or more platforms upon which app and sevices can be bulit.
- SaaS or SEaaS : Services as a Service
  - Serivces offered such as: address verification, Phone validation, Tax-rate calculation, SMS provider and so on
  - These are services that are provided by SEaaS providers.
  - Azure congnitive service fits into this category
- Surveying the cloud provider:
  - Criteria for choosing: markert share, revenue, fortune 500 client and most important one is performance in your desire service.
  - AWS is the leader in overall cloud servies but that not the case for every cloud niche services
  - Check market leader under specific categry where you want to invest like  IaaS/SaaS/PaaS/SEaaS
  
## Azure Basics
- Subscription: Its a subscription based service for different areas:
  - Businesses can get Azure by:
    - Sign up on portal
    - Add Azure to their existing enterprise aggrement
    - Consult to a Microsoft cloud solution provider(CSP)
  - For US government :
    -   Option to buy through Azure government licennsing provider
    -   Available with no upfront payment options
    -   Available for fedral, state, local and tribal government agencies
  - For Non profit:
    -  Azure gives price points for apps like .Dynamic 365, Power platform, Microsoft 365, linkedin and Azure
    -  for small NGOs, plan starts at zero cost and increses as organisation scales up
    -  Azure gives yealy $3500 grants for NGOs, need to apply for a grant
  - For student: for student no credit card required for free account and also get free credit of $100 with 25 products
  - For individual: Sign up for free trial and get 1 year free acees to serivces and $200 creadit
- Cost of Azure services:
  - We can see cost in estimate tab (cost calculator) when we are selecting services like, VMs, DB servers, licences. We can also see variuos proces option like pay as you use or buy service for fixed period say 1-2 years with discount.
  - We can also set limit on billing after that price Azure gets disabled.
  - The broad world of Azure services: You can just oversee the services Azure provides under different categories like IoT, Storage, DevOps and so on.

## Hosting
- Azure app services overview
  - Hosting Options
    - Azure app service(PaaS): Best app service
    - Service Fabric(PaaS): good for microservice architecture, it makes it easy to package, manage and deploy contenarize or non-containerized microservice.
    - Azure Virtual Machine(IaaS): in case you want to manage your VM. we can just migrate existing Web app on VM. You are responsible for configuring, maintaining and patching of environment. 
  - App service is a hosting service for web applications, REST APIs and mobile backends.
  - It provides platform abstraction built upon Azure VMs layer. OS and webserver are abstracted. We can choose from preconfigured servers(linux\windows)
  - Benefits:
    - Write app in multiple languages
    - Support DevOps tools like docker hub, Azure container
    - Security and complaince: App service is ISO, SOC and PCI compliant plus you can create IP restriction and manage accees by entities.
    - More than 50 connectors for SaaS provider
- Website and webapp
  - When we create a webapp on app service, Azure creates:
    - Virtual machine
    - Install pre configured OS
    - Install pre-configured webservers
  - Next step is create content depndeing on type of web app and deploy it using VS Code or VS Studio
  - We can jump start using existing app service templates
  - Below files are deployed at web app or websites:
    - Markup(HTML, CSS)
    - Content(Image, audio, video)
    - Client side scripts (Javascript)
    - Server side code (PHP, C#)
- App service and plan
  - App service plan means preconfigured environment
  - A App service plan can have multiple App services hosted in it
  - Billing is made on App service plan and not on app service.
  - We can add mutiple app service in an plan, it will not affect cost but the performance
- Build a app service on Azure
  - We need to create a service plan if one not already there or you want to create a new one
    - Goto Service plan option in azure portal
    - Create a service plan, give a name to service plan under "resource group" text box, select OS and region, select a free tier as dev/Test under section 'pricing tier' then click on "review and create"
  - Goto "App service" Then click on create button to create a app serivice
    - Select app service plan under "resource group" dropdown
    - Give unique name as this will be your end point to use app
    - Select language (Python), OS and region
- Edit and publish web app files: Using Visual studio publish your website to Azure
## API and API Management































