# Questions

## Beginner

### General Cloud Questions

<details>
<summary>1. What are the different types of services offered in the cloud?</summary>

>**Answer:**
>#### IAAS
>In infrastructure as a service, you get the raw hardware from your cloud provider as a service i.e you get a server which you can configure with your own will.
>#### PAAS
>Platform as a Service, gives you a platform to publish without giving the access to the underlying software or OS. 	
>#### SAAS
>You get software as a service in Azure, i.e no infrastructure, no platform, simple software that you can use without purchasing it.
</details>

<details>
<summary>2. What are the different cloud deployment models?</summary>

>**Answer:**
>#### Public Cloud
>The infrastructure is owned by your cloud provider and the server that you are using could be a multi-tenant system.
>#### Private Cloud
>The infrastructure is owned by you or your cloud provider gives you that service exclusively. For eg: Hosting your website on your servers, or hosting your website with the cloud provider on a dedicated server.
>#### Hybrid Cloud
>When you use both Public Cloud, Private Cloud together, it is called Hybrid Cloud. For Example: Using your in-house servers for confidential data, and the public cloud for hosting your company’s public facing website. This type of setup would be a hybrid cloud.
</details>

<details>
<summary>3. Why do we need CI/CD?</summary>

>**Answer:**
>#### CI
>The 'CI' always refers to continuous integration, which is an automation process for developers. Successful CI means new code changes to an app are regularly built, tested, and merged to a shared repository. It’s a solution to the problem of having too many branches of an app in development at once that might conflict with each other.
>#### CD
>The 'CD' refers to continuous delivery and/or continuous deployment, which are related concepts that sometimes get used interchangeably. Both are about automating further stages of the pipeline, but they’re sometimes used separately to illustrate just how much automation is happening.
</details>

### Basic Azure Questions

<details>
<summary>1. What is Azure Active Directory (Azure AD)?</summary>

>**Answer:**
>Azure AD is a cloud-based IAM solution and directory by Microsoft. It brings together application access management, core directory services, and identity protection and turns them into a single solution. It helps employees of an organization sign in and access resources such as:
> * External resources, including Microsoft 365, the Azure portal, and a big number of SaaS applications
> * Internal resources, such as apps on a corporate network and intranet, as well as any cloud-based apps built by that organization
</details>

<details>
<summary>2. What are Azure resources?</summary>

>**Answer:**
>Any entity managed by Azure can be referred to as an Azure resource. The following are some examples of Azure resources: Storage accounts, virtual networks, virtual machines, etc.
</details>

<details>
<summary>3. What is Azure Resource Manager?</summary>

>**Answer:**
>Azure Resource Manager, offered by Azure, provides management and application deployment in Azure. The management layer helps to build, modify, or delete resources in the Azure subscription account. It is useful while managing access controls, locks, and security of resources.
</details>

<details>
<summary>4. What is autoscaling in Azure?</summary>

>**Answer:**
>Autoscale is an inbuilt feature of Cloud Services, Virtual Machine Scale Sets, and Websites that enables applications to expand to adapt to changing demand. Scaling out refers to increasing the number of instances in a system. The amount of manual work necessary in dynamically scaling an application is reduced with an autoscaling solution.
</details>

<details>
<summary>5. What is Azure Cache for Redis?</summary>

>**Answer:**
>Azure Cache for Redis provides an in-memory data store based on the Redis software. Redis improves the performance and scalability of an application that uses backend data stores heavily. It's able to process large volumes of application requests by keeping frequently accessed data in the server memory, which can be written to and read from quickly. Redis brings a critical low-latency and high-throughput data storage solution to modern applications.
</details>

<details>
<summary>6. Define Azure storage key</summary>

>**Answer:**
>Azure storage key is used to authenticate access to Azure storage service data depending on the project requirements. There are two types of storage keys that are used for authentication:
> * Primary access key
> * Secondary access key, to avoid downtime of the website or application
</details>

<details>
<summary>7. What is the Azure Content Delivery Networks?</summary>

>**Answer:**
>A content delivery network (CDN) is a decentralized network of servers that delivers web information to users quickly and effectively. In order to reduce latency, CDNs keep buffer data on edge nodes in point-of-presence (POP) locations close to target users. Whether you are building or maintaining websites or mobile apps, encrypting and delivering streaming services, system updates, etc., the Azure Content Delivery Network (CDN) can help you minimize the page load time, reduce bandwidth, and improve responsiveness.
</details>

<details>
<summary>8. What is Azure App Service?</summary>

>**Answer:**
>Azure App Service is a completely managed Platform-as-a-Service (PaaS) offering for proficient developers that conveys a rich arrangement of abilities to the web, mobile, and integration scenarios. Mobile apps in Azure App Service offer a very adaptable, universally accessible mobile application development platform for Enterprise Developers and System Integrators that conveys a rich set of capacities to mobile engineers.
</details>

<details>
<summary>9. What is Azure Functions?</summary>

>**Answer:**
>The Azure Functions is a serverless code computation service that allows you to run code without a server on demand, such as Events and External-Invoke. They are stateless and short-lived, and azure Functions may automatically scale up in response to the request. They tend to speed up the development process by avoiding the need to perform any integration coding for you to connect to other services. They also offer Azure Application Insights for monitoring and evaluating code performance, which aids in the identification of bottlenecks and failure locations throughout the application's components. You can write Functions in C#, Node, Java, Python, and other languages.
</details>

## Intermediate

### General Azure Questions

<details>
<summary>1. What is Azure Blob Storage?</summary>

>**Answer:**
>Azure Blob (binary large object) storage is the object storage solution for the cloud. It is capable of storing large unstructured data in text or binary format and is suitable for serving documents, media, or text to the browser directly. The data is accessible from anywhere.
>The blobs are grouped into containers and tied to user accounts. This service has three components:
>* **Storage account**: This can be a general storage account or a blob storage account registered in Microsoft Azure.
>* **Container**: Containers are used for grouping blobs. Each container can store an unlimited number of blobs. The container name should be in lowercase.
>* **Blob**: A blob is a file or document of any type and size. Three kinds of blobs are supported by Azure:
>   * **Block blobs**: Text and binary files up to 195GB, 50,000 blocks of maximum 4 MB each
>   * **Append blobs**: Appends operations such as logging data in log files
>   * **Page blobs**: For frequent read or write operations
</details>

<details>
<summary>2. What are the different types of Storage data services in Azure?
</summary>

>**Answer:**
>The Azure Storage platform includes the following data services:
> * **Blobs**: A massively scalable object store for text and binary data.
> * **Files**: Managed file shares for cloud or on-premises deployments.
> * **Queues**: A messaging store for reliable messaging between application components.
> * **Tables**: A NoSQL store for schemaless storage of structured data.
> * **Disks**: Block-level storage volumes for Azure VMs.
> * **Elastic SAN**: A fully integrated solution that simplifies deploying, scaling, managing, and configuring a SAN in Azure.
</details>

<details>
<summary>3. What is Conditional Access in Azure?</summary>

>**Answer:**
>Conditional Access is used by Azure AD as a tool to make decisions, bring signals together, and impose organizational policies.
>Through Conditional Access policies, one can implement the right access controls whenever required to keep the organization secure and stay out of the users’ way when not needed.
</details>

<details>
<summary>4. How many types of backups are there in Azure?</summary>

>**Answer:**
>Azure Backup includes three types of replications that keep both storage and data highly available.
> * **Geo-redundant storage (GRS)**: The default and recommended option that replicates data to a secondary region far from the primary location
> * **Locally redundant storage (LRS)**: Creates three copies of the data in a storage scale unit within a data center
> * **Zone-redundant storage (ZRS)**: Replicates the data in availability zones with data residency and resiliency in the same region and has no downtime
</details>

<details>
<summary>5. What is the Azure Cognitive Search?</summary>

>**Answer:**
>Azure Cognitive Search is a cloud search solution that entrusts server and infrastructure maintenance to Microsoft. It provides developers with platforms, APIs, and tools for creating ready-to-use advanced search experiences in web, mobile, and corporate applications over private, diverse content. By using a simple REST API or client libraries in Azure SDKs, you can easily add a powerful search experience to your applications without having to manage search infrastructure or become a search specialist. For apps that depend exclusively on the search for both feature extraction and content navigation, Azure Cognitive Search is the ideal cloud provider for full-text search operations over content repositories and databases on Azure.
</details>

<details>
<summary>6. What do you understand by Azure Scheduler?</summary>

>**Answer:**
>Azure Scheduler helps us to invoke certain background trigger events or activities like calling HTTP/S endpoints or to present a message on the queue on any schedule.
>
>By using this Azure Schedule, the jobs present in the cloud call services present within and outside of the Azure to execute those jobs on-demand that are routinely on a repeated regular schedule or start those jobs at a future specified date.
</details>

<details>
<summary>7. Explain the Site Recovery feature of Azure.</summary>

>**Answer:**
>Site Recovery is a service that keeps corporate apps and workloads operational during outages, assuring smooth business processes. This feature offered by Azure works in such a way that it copies activities from a primary location to a secondary location with the help of physical and virtual machines (VMs). When your primary location goes down, you switch to the secondary location, where you can access the apps. You can roll back to the principal location once it has been restored. Site Recovery ensures replication for Azure VMs, on-site VMs, Azure Stack VMs, and physical servers.
</details>

<details>
<summary>8. What is meant by Azure Service Fabric?</summary>

>**Answer:**
>Azure Service Fabric is a parallel processing platform that ensures simple packaging, smooth deployment, and efficient handling of robust and reliable microservices and containers. Service Fabric allows you to create microservice-based applications. The major constraints in designing and administering cloud-native apps are also handled by Service Fabric. It has a huge emphasis on designing stateful services. You can run container-based stateful services written in any language or code using the Service Fabric computing architecture. Also, you can create Service Fabric clusters in the private clouds with Windows Server and Linux, as well as in other public clouds.
</details>

<details>
<summary>9. What is the Azure Data Lake?</summary>

>**Answer:**
>A data lake is a centralized repository that ingests and stores large volumes of data in its original form. The data can then be processed and used as a basis for a variety of analytic needs. Due to its open, scalable architecture, a data lake can accommodate all types of data from any source, from structured (database tables, Excel sheets) to semi-structured (XML files, webpages) to unstructured (images, audio files, tweets), all without sacrificing fidelity. The data files are typically stored in staged zones—raw, cleansed, and curated—so that different types of users may use the data in its various forms to meet their needs. Data lakes provide core data consistency across a variety of applications, powering big data analytics, machine learning, predictive analytics, and other forms of intelligent action.
</details>

<details>
<summary>10. What is the Azure Data Factory?</summary>

>**Answer:**
>Azure Data Factory is a serverless and cloud-based data integration service and platform used for the creation of ETL and ELT pipelines. It helps in the creation of data-driven workflows for the planning and execution of data movements and data transformation at scale.
</details>

<details>
<summary>11. What is the Azure Databricks?</summary>

>**Answer:**
>Azure Databricks is a Data Analytics platform that offers two environments for the development of data-intensive applications: 
> * Azure Databricks SQL Analytics
> * Azure Databricks Workspace
>Azure Databricks integration with the security, compute, analytics, storage, and AI services that are natively provided by cloud providers facilitate the unification of data and AI workloads.
</details>

### Azure Cosmos DB
<details>
<summary>1. What is Azure Cosmos DB?</summary>

>**Answer:**
>Azure CosmosDB is one of the PaaS features offered by Microsoft. It is a cloud-based NoSQL database that deals mainly with modern app development. CosmosDB data can be easily shared and replicated anywhere in the world, which ensures faster and more efficient app development. Capacity management, automatic scaling, and serverless databases aid in matching demand with storage capacity.
>
>Azure Cosmos DB takes care of database administration for you, including auto-management, updates, etc., and also includes features such as single-digit millisecond response times, rapid scalability, SLA-backed availability, and enterprise-grade privacy.
</details>

<details>
<summary>2. Which Cosmos DB component will you use if you need to provide your application temporary access to Cosmos DB?
</summary>

>**Answer:**
>The two URLs, Read and Read-Write, allow you to share your Azure Cosmos DB account with other people for a specified duration of time. Since the account access has an expiration time window of 24 hours, you can regain access by using a newly-generated access URL or the connection string.
> * Read URL- Other users can browse the databases, collections, queries, and other resources linked with that specific account, provided you share the read-only URL with them. 
> * Read-Write URL- Other users can read and alter the databases, collections, queries, and other resources linked with that specific account if you share the Read-Write URL with them.
</details>

### Azure SQL

<details>
<summary>1. What is SQL Azure database?</summary>

>**Answer:**
>Azure SQL is a family of managed, secure, and intelligent products that use the SQL Server database engine in the Azure cloud.
>Azure SQL Database is a relational database-as-a-service (DBaaS) hosted in Azure that falls into the industry category of Platform-as-a-Service (PaaS).
</details>

<details>
<summary>2. What are SQL elastic pools?</summary>

>**Answer:**
>Azure SQL Database elastic pools are a simple, cost-effective solution for managing and scaling multiple databases that have varying and unpredictable usage demands. The databases in an elastic pool are on a single server and share a set number of resources at a set price. Elastic pools in SQL Database enable software as a service (SaaS) developers to optimize the price performance for a group of databases within a prescribed budget while delivering performance elasticity for each database.
</details>

<details>
<summary>3. How can you make a SQL Azure Database perform better?</summary>

>**Answer:**
>The execution plan and statistics of a query can be used to tune a SQL Azure database. To monitor and manage SQL Azure databases, you can use SQL Azure's Dynamic Management views. Network latency and bandwidth also have an impact on SQL Azure performance. In this case, the best performance comes from code that is close to the application topology.
</details>

<details>
<summary>4. In Azure Synapse Analytics, what does a dedicated SQL pool mean?</summary>

>**Answer:**
>The enterprise data warehousing solutions included in Azure Synapse Analytics are referred to as a dedicated SQL pool. When using Synapse SQL, a dedicated SQL pool constitutes a group of analytic tools that are deployed. Data Warehousing Units are solely responsible for determining the size of a dedicated SQL pool. Once the dedicated SQL pool is established, you can use basic PolyBase T-SQL queries to import massive amounts of data and then leverage the distributed data processor to run high-performance analyses. As data gets merged and analyzed, a dedicated SQL pool becomes the only source your company can rely on for reliable high-speed insights.
</details>

### Azure Virtual Machines

<details>
<summary>1. How can you have a common file-sharing system among multiple virtual machines?</summary>

>**Answer:**
>Azure files system is used as a common repository system for data sharing among virtual machines that are configured using protocols such as NFS, FTPS, SMB, etc.
</details>

<details>
<summary>2. Is it possible to create a Virtual Machine using Azure Resource Manager in a Virtual Network that was created using classic deployment?</summary>

>**Answer:**
>This is not supported. You cannot use Azure Resource Manager to deploy a virtual machine into a virtual network that was created using classic deployment.
</details>

<details>
<summary>3. What are virtual machine scale sets in Azure?</summary>

>**Answer:**
>Virtual machine scale sets are Azure compute resource that you can use to deploy and manage a set of identical VMs. With all the VMs configured the same, scale sets are designed to support true autoscale, and no pre-provisioning of VMs is required. So it’s easier to build large-scale services that target big compute, big data, and containerized workloads.
</details>

<details>
<summary>4. Are data disks supported within scale sets?</summary>

>**Answer:**
>Yes. A scale set can define an attached data disk configuration that applies to all VMs in the set. Other options for storing data include:
> * Azure files (SMB shared drives)
> * OS drive
> * Temp drive (local, not backed by Azure Storage)
> * Azure data service (for example, Azure tables, Azure blobs)
> * External data service (for example, remote database)
</details>

<details>
<summary>5. What is an Availability Set?</summary>

>**Answer:**
>An availability set is a logical grouping of VMs that allows Azure to understand how your application is built to provide redundancy and availability. It is recommended that two or more VMs are created within an availability set to provide for a highly available application and to meet the 99.95% Azure SLA. When a single VM is used with Azure Premium Storage, the Azure SLA applies for unplanned maintenance events.
</details>

<details>
<summary>6. Is it possible to add an existing VM to an availability set?</summary>

>**Answer:**
>No. If you want your VM to be part of an availability set, you need to create the VM within the set. There currently no way to add a VM to an availability set after it has been created.
</details>

<details>
<summary>7. What would be the best feature recommended by Azure for having a common file sharing system between multiple virtual machines?</summary>

>**Answer:**
>Azure provides a service called Azure File System which is used as a common repository system for sharing the data across the Virtual Machines configured by making use of protocols like SMB, FTPS, NFS, etc.
</details>

## Advanced

### General Azure Questions

<details>
<summary>1. What are the different storage services available in Azure apart from Blob storage?</summary>

>**Answer:**
>Azure offers three other types of storage services, apart from Blob storage, table storage, queue Storage, and file storage.
> * **Azure table storage**: It allows the deployment of applications with semi-structured data and a key-value store, which is NoSQL-based.
>   * Used when there is a requirement for applications with a flexible data schema
>   * Emphasis is on enterprise-level data and strongly follows consistent models
>   * Data is in terms of entities grouped under tables
> * **Azure queue storage**: The message queue system is capable of handling large workloads through the development of flexible and durable applications.
>   * Ensures that the applications are scalable and less likely to have component failures
>   * The queue monitoring helps the application ensure that the requirements are met
> * **Azure file storage**: It offers file sharing and access using server message block (SMB) protocol. The data is secured with SMB 3.0 and HTTPS.
>   * Improves the performance of on-premise applications
>   * Azure takes care of OS deployments and hardware management

</details>

<details>
<summary>2. What is the difference between Azure Table Storage and the Azure SQL service?</summary>

>**Answer:**
>The major difference is that Azure SQL uses a relational storage structure and Azure Table follows centralized structured data without relations.
</details>

<details>
<summary>3. What is the difference between Service Bus Queues and Storage Queues?</summary>

>**Answer:**
>The Azure Storage Queue uses the local Azure Storage Emulator and debugging is made quite easy. The tooling for Azure Storage Queues allows you to easily peek at the top 32 messages and if the messages are in XML or Json, you’re able to visualize their contents directly from Visual Studio Furthermore, these queues can be purged of their contents, which is especially useful during development and QA efforts.
>
>The Azure Service Bus Queues are built into the Service Bus and are able to forward messages to other Queues and Topics. They have a built-in dead-letter queue and messages have a time to live that you control, hence messages don’t automatically disappear after 7 days.
>
>Furthermore, Azure Service Bus Queues have the ability of deleting themselves after a configurable amount of idle time. This feature is very practical when you create Queues for each user, because if a user hasn’t interacted with a Queue for the past month, it automatically gets clean it up. Its also a great way to drive costs down. You shouldn’t have to pay for storage that you don’t need. These Queues are limited to a maximum of 80gb. Once you’ve reached this limit your application will start receiving exceptions.
</details>

<details>
<summary>4. What are the two different types of data flow transformations in Azure Data Factory?</summary>

>**Answer:**
> * **Mapping data flow**: This is a visually oriented data transformation task that allows users to create graphical data transformation logic without the need for any expert/professional.
> * **Wrangling data flow**: This is a Power Query Online-integrated data preparation process that doesn't require any coding.
</details>