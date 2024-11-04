---
layout: article-toc
---
# General FAQs
## What If I need a copy of my data what is involved, and how frequently can I get hold of it?

Firstly it's your data so by definition you are entitled to ask for a copy. Should you need a copy all you need to do is provide Hornbill with notice that you require this, typically no less than 14 days notice is required, and we will make available a copy of your data. Hornbill will provide a copy of your data by request once every 90 days at no additional cost.  Your data will archived, compressed, encrypted and placed on our servers and you will be notified via email when its available and will have 7 days to download it to your servers.  If you want these more frequently then you should consider the [[Hornbill Data Assurity]] service.

Hornbill Data Assurity is an optional chargeable subscription add-on service where we proactively archive and deliver a complete copy of your customer data to a cloud service of your choosing that you control (Amazon S3 for example) on a more regular, scheduled basis, typically once a month.

## Who is entitled to ask for a copy of my data to be provided?

Only the named Account Authority for your instance can make a request for a copy of your customer data to the Hornbill Cloud team. Any other requests will be referred back to the named Account Authority.

## My security team have asked to know where the data is held?

All data is held in the geographical legal entity associated with the instance. Therefore if your instance is in Europe your data remains in Europe, if your instance is in North America your data remains in North America.

## Is the data encrypted and secure both in motion and at rest?

Data is encrypted both in motion and at rest, in addition, our choice of data centre\infrastructure\product architecture\processes and general working ethos ensure that data is secure at all times. Full encryption at rest is applied across the board.  All data in motion is encrypted either via HTTPS\TLS 1.2/3 and verified trusted SSL certificates are used at all times.

## Does Hornbill regularly undertake penetration testing against the service?

Yes. As well as frequent tests undertaken by Hornbill we utilize external security companies to validate our results and services at least annually. Results of tests are available on request.

## Under Data Protection legislation, my legal team want to know who will have access to the data?

Access to data is restricted to your employees (with granular access rights available to limit subsets of data to different teams) and anyone you grant access to. The Hornbill cloud team have access to the servers\databases, however ISO requirements and processes mean that we would first need to obtain authorisation from your nominated contacts before accessing your instance data (All access to servers are logged and reviewed to ensure that this requirement is met).

## How much storage do I get on my Hornbill instance, and what happens if I need more?

By default your instance is automatically provisioned with 30GB of Storage. Additional storage is available should you require it and is charged at £0.20 per GB.

## How long does Hornbill retain the data for if we cancel our subscription?

In the event you choose to terminate your agreement Hornbill will retain your customer Data for a period of 30 Days from the Date of Termination. We will of course provide you with a copy of this data upon request in an industry standard machine readable format.

## Does Hornbill perform background checks on personnel with administrative access to servers, applications and customer data?

We handle customer data in our roles as a data processor as well as acting as a data controller for our company data, and we take this responsibility very seriously. To operate to the highest level of security and quality, and to meet the General Data Protection Regulation, as well as our own information security policies, we undertake security screening for all employees to the BS7858:2012 standard. 

This British Standard covers the following areas which tick all the necessary boxes as far as our security requirements are concerned:
* Proof of identity
* Proof of residence
* References
* A copy of their police record (if any)
* A statement of financial status
* A history of all employment (going back five years or to 12 years’ old, whichever occurs first)
* And/or a school report
* Current work permits or visas (foreign nationals)

## What measures are in place for Data Transfer Security?
All data in motion between instance and client (Web Browser) is encrypted via HTTPS\SSL. All other data in transit is encrypted via other secure protocols. No data is ever transmitted in clear text.

## What Happens with our data after we terminate our subscription
Upon any termination, Hornbill shall use reasonable endeavors to assist in the migration of the Customer’s data and documents to another system within 20 working days. Such assistance to be subject to Hornbill’s terms for time and materials consultancy services and its associated standard day rates. Hornbill also agrees that such estimates for work will be reasonable and appropriate to the scale of request received for such data. Hornbill will delete (see below) the Customer Data between 30 and 60 days after the termination date. This includes all backups and data relating to those backups (Replications, Keys, Catalogs etc.

A SQL data dump will be provided of your instance (All SQL Create\Insert statements for your data) and the copy of File Attachments via Secure FTP within a password encrypted ZIP.  An email is then sent to the primary technical contact for the instance containing information about the data drop along with the key required to unencrypted the content.

## Is it possible to restrict access to my Hornbill instance by IP address ranges?
In some enterprise environments its desirable to restrict access by source IP address. It is important that Hornbill's service is made up of two distinct layers, the presentation layer and the data layer.  The presentation layer is the HTML content, this is shared amongst all customers and specifically has no customer-specific data served at this layer. The presentation layer is cached in a public cache (Cloudflare) for optimal global performance. It is not possible to restrict access to these caches via IP address range. The second layer, our data layer is all accessed via an API endpoint that is specific to your instance.  For API access,  Hornbill allows you to set one or more IP address matching rules, and if you have one or more rules set, only API calls that originate from IP addresses that match the rule(s) will be allowed.   This functionality is pat of our advanced enterprise security feature-set and is only available for customers subscribed to the [https://www.hornbill.com/editions/ Enterprise Edition] of the Hornbill Platform.

Setting an IP restriction will not prevent the UI pages from loading, but if your browser is not in an IP address range that is in your defined allowed IP address rules then you will not be able to log into, or access your instance from a non-whitelisted IP address. 

It should be noted that by adding such restrictions, it is generally not possible to know the IP address(es) where mobile data comes from, so if you use IP address restrictions it is likely that you will not be able to use the Hornbill Mobile app unless wifi is enabled and your device gets allocated an IP address that falls within a rage that the rules you have created allow.

## What Happens to my data when it is translated using Google Translate
To implement our translation capability, we use Google's translate service, via the Google Translation API.  At the point you choose to translate any given text, our service will send that text to Google via the Translate API, and Google will return the translated version of that text.   The full details of exactly how Google processes data is described in their terms here: https://cloud.google.com/translate/data-usage You can see a full list of our data sub-processors and the service we use to support our service here: https://wiki.hornbill.com/index.php/FAQ:Subprocessors

The summary of these terms states that Google will temporarily store the data on their servers for the sole purpose of performing the requested translation, your data is not shared with anyone or made public in any way, and is removed from Google's servers within a day or two.

If you are uncomfortable with your data being sent to Google's servers there is an option to disable this capability on your instance.


## Delete v Wipe 
For Storage devices no longer used. Hornbill does not simply "delete" data as this can be restored, we destroy data via wiping and this is achieved by overwriting all data blocks associated to a given file\logical volume or storage device firstly with 1s and then 0s. No data is left intact. 

Physical disks (Used by underlying hardware not virtual disks that the instances run on) under go the same process as above and are then destroyed on premise with certificate of destruction obtained.


## How does the Hornbill authenticate to a customer’s directory service such as Active Directory?
Hornbill employes an open standard called SAML 2.0, it's a secure, robust, enterprise-class authentication scheme that is industry standard.  More can be found here: https://en.wikipedia.org/wiki/SAML_2.0  and details specific to Hornbill's implementation can be found here: https://wiki.hornbill.com/index.php/Single_Sign_On_with_SAML_2.0

## How is the authentication secret protected on hornbill’s systems?  Any multiple factors for authentication or restrictions/protections?
All authentication secrets are stored either hashed or encrypted, only the lastest known-to-be-secure schemes are used, for hashing we generally use SHA1-256 and for encryption AES256. Multi-factor authentication can be enabled against Hornbill Authentication from our own 2FA functions or via your own security provider such as ADF\SAML

## How is the separation between customer data enforced/controlled in infrastructure and/or logically?
The Hornbill platform segments every customer's dataset into an "instance", you can think of an instance as a data sandbox  Each instance gets a dedicated database and dedicated file storage. Data isolation is achieved at the lowest layers of our stack. For the database, each instance has a database, and while multiple databases sit on the same physical server, each database has access credentials specific only to the instance to which it belongs.  For filesystem (file attachment storage etc), data is segregated based on the instance. The design of our application stack ensures that sessions are keyed to an instance using cryptographic techniques to make it impossible for one customer's dataset to be cross-contaminated with any other customers dataset.

## How are resources allocated within the Cloud/SaaS platform? Who/what gets priority? SLA?
Resources are allocated commensurate with the size of the instance (number or subscribed users) as well as by workload demand. Workload priority is based on ensuring that individual API calls complete within timings set based on the class of the API, and we adjust resources according to those rules. It is in Hornbill's commercial interests to always keep our service performant and available, and we consistently achieve well above our target of 99.95%, you can see our service performance metrics here: https://status.hornbill.com/

## What are the different Editions of Hornbill
https://wiki.hornbill.com/index.php?title=Hornbill_Editions

<!-- https://beta.hornbill.com/hornbill/post/urn:buzz:activity:15d3f6ed-7d01-46e9-af65-c4b6f6a0bb7e -->
<!-- https://docs.hornbill.com/hornbill-cloud/data-security-commitment -->

## Was Hornbill's architecture designed or reviewed by a qualified security architect?
It is very difficult to state in absolute terms what a qualified security architect is, but, Hornbill's technology stack and system design has been built over three decades by a team of professionals that have many decades of combined experience and expertise, designing, building and operating complex cloud software and business applications that meet, often exceed continuously review security needs.  Our systems are continuously monitored, reviewed and tested against maintained and certified security standards including ISO27001 and ISO27018, we undertake penetration testing exercises and have all the features required for securing, monitoring and auditing all aspects of the systems operation in relation to security concerns. We have operated a robust SaaS solution for over 15 years, with zero incidents of data loss or security breaches in that time, whilst consistently maintaining five nines system availability.

