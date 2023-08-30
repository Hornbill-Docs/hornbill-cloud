---
layout: article-toc
---
# Data Storage
Hornbill measures space used by your personal data. It does not measure disk space used by our software or any infrastructure components we deploy in order to deliver the Hornbill service. The measurement is broken down into two separate domains known as [Disk Storage](#disk-storage) and [Database Storage](#database-storage). 

## Disk Storage
Files are stored using Content Addressable File Store (CAFS) technology. Each customer has their own CAFS store. The following elements of an instance contribute toward disk storage usage:
* File Attachments (e-mails, posts, entity records, requests, tasks, etc...)
* Content Indexes
* Embedded Images
* Documents (uploaded into Document Manager)
* Installed Apps
* Any other large binary object

## Database Storage
The underlying database uses MariaDB and its storage engine determines the space utilized for a given database.  Each customer instance has its own dedicated database. The following elements of your instance contribute towards database storage usage
* Posts and comments in activities
* Tasks
* Customer, Contact, and other database records
* Documents (created in Document Manager)
* Business Processes
* Reports
* Any dynamic content that's added to your database through the APIs, forms, and integrations.

## Storage Quota and Utilization
Every Hornbill instance comes with 30Gb of storage and additional storage can be purchased when needed. We audit storage utilization daily and keep storage utilization history on the following basis: -

* Daily Database storage used for the last 90 days rolling
* Daily Disk storage used for the last 90 days rolling

:::tip
Your storage information can be seen in the Hornbill Solution Center
:::

## Storage Size Definition
There is sometimes confusion about abbreviated size values used in computing. For example, most uses of the team Gb mean Gigabyte, but there are two values this can mean, one is decimal, based on "1 byte x 1000 x 1000 x 1000" and the other is base 2, which is calculated as "1 byte x 1024 x 1024 x 1024). The modern interpretations of these size abbreviations are 1Gb = 1000000000 bytes and 1GiB = 1,262,485,504 bytes, and in general, a Gb is what is normally used. The problem with base 2 calculations is they are non-linear and do not work properly as the computing technology has reached the tera and peta byte scale, so the decimal scheme has been adopted generally, and this is true for the Hornbill platform. To for the avoidance of any doubt, the following table sets out what we mean when stating storage sizes in Mb, Gb, Tb, etc.


Storage Size Abbreviations
|Abbreviation|Size In Bytes|
|-|-|
|KB|1000 bytes|
|MB|1,000,000 bytes|
|GB|1,000,000,000 bytes|
|TB|1,000,000,000,000 bytes|

## Data Encryption
All data is physically stored on SSD or Hard Disks and is block-level encrypted at rest at all times. Furthermore, data is stored in a RAID configured disk set, spread across multiple physical disks making it impossible to extract any meaningful data without having all physical disks in a set to extract from. We use the industry-strength AES256 encryption scheme throughout and have a comprehensive key management system ensuring every physical and virtual server has its own set of string, unique keys for encryption.

## Data Segregation
Hornbill has been designed with special attention paid to the security of data, specifically, we wanted to achieve the maximum isolation between each customer's data as possible while still getting the benefit of multi-tenancy in deployment and upgrades. Hornbill is designed to deliver the best of both worlds to our customers by adopting a hybrid data isolation model. To best explain Hornbill's data isolation model we first need to describe the more traditional models.

### Multi-Instance Model
This model provides a high level of data isolation because a fully independent instance of the software, database, and other components is running in full isolation for each and every customer. Typically this is delivered by providing a dedicated instance of an operating system (Linux or Windows etc) upon which a copy of the service provider's software is running as well as the data set needed to support the customer's specific instance. An example of this kind of SaaS architecture might be ServiceNow and Myservicedesk.com (Supportworks in the cloud).

#### Advantages
* Data Isolation is achieved at the operating system level
* Compute resources can be allocated/dedicated to individual customers
* Customers can run specific versions of the vendor's software in their specific instance
#### Disadvantages
* Web-scale expandability is difficult to achieve, compute resources are finite as they are tied to virtual machine/operating system compute resources
* Customers may find themselves not able to upgrade, the flexibility of running/locking down on individual versions of the software creates this problem as the software designers are not forced into considering the upgradability of every customer's individual changes/customizations, this is especially true when customizations require code to be developed as part of the customization
### Multi-Tenant
This model provides data isolation at the application layer which means that every customer's data is stored in the same database and the application code ensures that data for each customer is only served to that customer. Properly implemented it is generally safe and reliable and has many large-scale proven applications deployed today. There are some big advantages but these are mostly weighted to the benefit of a service provider who in turn delivers benefits back to the customer through economies of scale and therefore price (in theory at least). Salesforce.com is a good example of a solution that adopts this model.
#### Advantages
Web-scale expandability is easier to achieve as the same computer resources are shared with all customers at the same
All customers are on the same version of the software, which means all customers get all upgrades all of the time (think Facebook or Gmail)
Any customizations done by customers for their own use have to be completely isolated (and therefore protected) during updates - this imposes the right behaviors on the software designers and development teams
#### Disadvantages
Customers have no control over the versions of the software they use, they have to be prepared to consume the software as a service
The risk of data leaking is moved up the stack to the application layer, this means that the risk of unexpected data exposure is higher than lower-level data isolation.
Code developed in the application layer could expose data unintentionally.

### Hornbill's Model
There are pros and cons to both of the models described above and there are many more ways to deliver a SaaS solution than just those two extremes. Hornbill adopted a model that could best be described as a combination of those two approaches. It's hard to put a name to what we have built but we would describe it as having true multi-tenant architecture but with enterprise-class data isolation. The best way to explain this would be to set out what our primary design goals were at the time of designing our architecture and what we ultimately implemented.

Number one on our agenda is we wanted a data isolation model comparable to that found in a multi-instance mode.
Data access requires a two-phase model for controlling access. Every data storage scheme implements at least two layers of access control, the first of which is *instance awareness*, meaning every request for access to data has to be identifiable against a specific instance for every request and to every storage container if the storage container does not belong to the instance then the request will fail.
Each customers data is fully isolated at the lowest possible level, and each customer has their own database, with isolation provided at the database security level (so this is independent of Hornbill's own code and implemented at the infrastructure level away from the application code) using a unique system account per instance.
Each customer's file storage has to be fully isolated at the filesystem level and held within its own container, access to which is again fully instance context-aware. In addition to this, within a container, file storage uses a content addressable system which guarantees that addressable content is unique to its actual content, so even if there was some accidental cross-contamination of customers' data someone would need to guess the content ID (which is a cryptographically strong SHA-256 checksum of the actual content) which for all practical purposes is unachievable in any way that would create a usable exploit.
Web applications run on our front-end servers - all customers use the exact same versions of software running on the same front-end servers so compute resources can scale out infinitely horizontally based on load and demand.
Application servers also scale out horizontally without any theoretical limit. In practice, we organize our application services into PODs which provide workload distribution, durability, and resilience to hardware or network failures.
All customers run the same version of our software stack, and this forces good discipline and behavior in our software design, development, test, and deployment teams.

## Content Addressable File Store
As a general rule, storing large objects such as images, files, videos, and other large binary objects it is very inefficient to use an RDBMS as a storage scheme. SQL servers are great for structured data but are far from ideal for storing things like files. Hornbill stores large objects using our own CAFS technology, CAFS stands for "Contact Addressable File Store" which unlike a conventional filesystem has some very unique and desirable properties.
* Content is located by its unique fingerprint which is derived from the actual content of the file being stored.
* Every unique piece of content is atomic and movable
* Content inside a CAFS storage is automatically de-duplicated, in other words, the way the CAFS works guarantees that any content stored will only ever be stored once so its very space efficient.
* Content can be easily distributed across physical storage devices/servers/locations/geographies with minimal system management overhead.
Stale content (that is content that is rarely accessed or is effectively soft archived) can be moved to lower cost storage dynamically ensuring the most accessed and most up to date data is always held on and served high performance storage.

The bottom line is, our storage scheme is fast, efficient, and capable of effectively unlimited storage, delivered elastically and with no administrative overhead placed on our customers for management. Read more about what's under the hood here Content Addressable File Store

<!-- https://wiki.hornbill.com/index.php?title=Instance_Storage_Quota -->