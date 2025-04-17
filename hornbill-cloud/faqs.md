---
layout: article-toc
---
# General FAQs
## Generic Security questionnaires

### Hornbill’s Approach to Security and Compliance
At Hornbill, we are deeply committed to delivering secure and reliable cloud services. Our Information Security Management System (ISMS), certified to ISO 27001 and ISO 27018, ensures we meet internationally recognized standards for information security and data protection. This ISMS is publicly accessible and provides transparency into the rigorous policies, processes, and controls we have in place.

### Our Position on Security Questionnaires
* Empowering Customer Due Diligence
We understand that your InfoSec team must evaluate whether our policies and practices meet your organisation’s requirements. It is their responsibility to assess our documented ISMS and determine whether it aligns with your specific security and compliance needs.

* Limitations of Custom Questionnaires

Hornbill does not complete bespoke security questionnaires. These are often repetitive, quickly outdated, and do not account for the continuous improvements we make to our processes. Instead, we provide a publicly available ISMS framework that offers a comprehensive and up-to-date view of our security practices.

Access to Expertise
* For Enterprise customers, we offer a 30-minute consultation with a member of our Proffesional Services Team to address any critical questions not answered by our ISMS documentation.
* Non-Enterprise customers can explore service credit options for similar support.

### Why This Approach Works
* Transparency: Our public-facing ISMS ensures you have direct access to the up-to-date details necessary to make informed decisions.
* Customer Responsibility: Your InfoSec team is best placed to determine whether our practices and policies align with your organisation’s standards. We provide the information and transparency needed to support this evaluation.
* Efficiency:  By maintaining a centralized, regularly updated ISMS, we focus our resources on continually enhancing our security posture rather than repetitive administrative tasks. Where a question arises that is not addressed in our online documentation, please advise, and Hornbill shall publish a response in a timely manner.

Hornbill’s approach balances the need for security assurance with operational efficiency. By leveraging our publicly available ISMS and collaborating as needed, your organization retains full control over assessing our suitability while benefiting from a clear, reliable, and continuously updated framework.

We believe this process ensures a fair and transparent partnership and invite you to review our ISMS to begin your assessment.


## What if I need a copy of my data? What is involved, and how frequently can I get hold of it?

Firstly, it's your data. So by definition you are entitled to ask for a copy. Should you need a copy, all you need to do is provide Hornbill with notice that you require this. Typically, no less than 14 days notice is required, and we will make available a copy of your data. A data drop of your Hornbill instance will be provided on request (a number of CSV files of your data) on termination, or twice per year, and a copy of file attachments (which includes request attachments, email attachments, Document Manager documents, etc.) via Secure FTP within two password-encrypted ZIPs. An email is then sent to the contacts associated to the Hornbill instance containing information about the data drop along with the key required to unencrypt the content.

## Who can ask for a copy of my data?

Only the named Account Authority for your instance can make a request for a copy of your customer data to the Hornbill Cloud team. Any other requests will be referred back to the named Account Authority.

## My security team have asked: where is the data held?

All data is held in the geographical legal entity associated with the instance. Therefore, if your instance is in Europe, your data remains in Europe; if your instance is in North America, your data remains in North America.

## Is the data encrypted and secure both in motion and at rest?

Data is encrypted both in motion and at rest. In addition, our choice of data centers\infrastructure\product architecture\processes and general working ethos ensure that data is secure at all times. Full encryption at rest is applied across the board.  All data in motion is encrypted either via HTTPS\TLS 1.2/3, and verified trusted SSL certificates are used at all times.

## Does Hornbill regularly undertake penetration testing against the service?

Yes. As well as frequent tests undertaken by Hornbill, we utilize external security companies to validate our results and services at least annually. Results of tests are available on request.

## Under data protection legislation, my legal team have asked: who will have access to the data?

Access to data is restricted to your employees (with granular access rights available to limit subsets of data to different teams) and anyone you grant access to. The Hornbill Cloud team have access to the servers\databases, however ISO requirements and processes mean that we would first need to obtain authorisation from your nominated contacts before accessing your instance data. (All access to servers is logged and reviewed to ensure that this requirement is met).

## How much storage do I get on my Hornbill instance, and what happens if I need more?

By default, your instance is automatically provisioned with 30GB of storage. Additional storage is available should you require it and is charged at £0.20 per GB.

## How long does Hornbill retain the data if we cancel our subscription?

In the event you choose to terminate your agreement, Hornbill will retain your customer data for a period of 30 days from the date of termination. We will of course provide you with a copy of this data upon request in an industry-standard, machine-readable format.

## Does Hornbill perform background checks on personnel with administrative access to servers, applications, and customer data?

We handle customer data in our roles as a data processor as well as acting as a data controller for our company data, and we take this responsibility very seriously. To operate to the highest level of security and quality, and to meet the General Data Protection Regulation, as well as our own information-security policies, we undertake security screening for all employees to the BS7858:2012 standard. 

This British standard covers the following areas, which tick all the necessary boxes as far as our security requirements are concerned:
* Proof of identity
* Proof of residence
* References
* A copy of their police record (if any)
* A statement of financial status
* A history of all employment (going back five years or to 12 years’ old, whichever occurs first)
* And/or a school report
* Current work permits or visas (for foreign nationals)

## What measures are in place for data-transfer security?
All data in motion between instance and client (web browser) is encrypted via HTTPS\SSL. All other data in transit is encrypted via other secure protocols. No data is ever transmitted in clear text.

## What happens with our data after we terminate our subscription?
Upon any termination, Hornbill shall use reasonable endeavors to assist in the migration of the customer’s data and documents to another system within 20 working days. Such assistance is subject to Hornbill’s terms for time and materials consultancy services and its associated standard day rates. Hornbill also agrees that such estimates for work will be reasonable and appropriate to the scale of request received for such data. Hornbill will delete (see below) the customer data between 30 and 60 days after the termination date. This includes all backups and data relating to those backups (replications, keys, catalogs, etc.).

A SQL data drop will be provided of your instance (all SQL Create\Insert statements for your data) and the copy of file attachments via Secure FTP within a password-encrypted ZIP.  An email is then sent to the primary technical contact for the instance containing information about the data drop, along with the key required to unencrypted the content.

## Is it possible to restrict access to my Hornbill instance by IP address ranges?
In some enterprise environments, it is desirable to restrict access by source IP address. It is important that Hornbill's service is made up of two distinct layers: the presentation layer and the data layer.  The presentation layer is the HTML content; this is shared amongst all customers and specifically has no customer-specific data served at this layer. The presentation layer is cached in a public cache (Cloudflare) for optimal global performance. It is not possible to restrict access to these caches via IP address range. The second layer, our data layer, is accessed via an API endpoint that is specific to your instance. For API access, Hornbill allows you to set one or more IP address matching rules. If you have one or more rules set, only API calls that originate from IP addresses that match the rule(s) will be allowed. This functionality is part of our advanced enterprise security feature set and is only available for customers subscribed to the [Enterprise Edition](https://www.hornbill.com/editions/) of the Hornbill Platform.

Setting an IP restriction will not prevent the UI pages from loading, but if your browser is not in an IP address range that is in your defined allowed IP address rules, then you will not be able to log into, or access your instance from a non-allowlisted IP address. 

:::note
By adding such restrictions, it is generally not possible to know the IP address(es) where mobile data comes from. So if you use IP address restrictions, it is likely that you will not be able to use the Hornbill Mobile app unless wifi is enabled and your device gets allocated an IP address that falls within a range that the rules you have created allow.
:::

## What happens to my data when it is translated using Google Translate?
To implement our translation capability, we use Google's translate service, via the Google Translation API. At the point you choose to translate any given text, our service will send that text to Google via the Translate API, and Google will return the translated version of that text. The full details of exactly how Google processes data is described [in their terms](https://cloud.google.com/translate/data-usage). You can see [a full list of our data sub-processors and the service we use to support our service](/hornbill-cloud/subprocessors).

The summary of these terms states that Google will temporarily store the data on their servers for the sole purpose of performing the requested translation. Your data is not shared with anyone or made public in any way, and is removed from Google's servers within a day or two.

If you are uncomfortable with your data being sent to Google's servers, there is an option to disable this capability on your instance.

## How does Hornbill authenticate to a customer’s directory service such as Active Directory?
Hornbill employs an open standard called SAML 2.0, which is a secure, robust, enterprise-class authentication scheme that is industry standard. More information can be found [on Wikipedia](https://en.wikipedia.org/wiki/SAML_2.0) and see also [details specific to Hornbill's implementation](/esp-config/security/sso/sso-with-saml).

## How is the authentication secret protected on Hornbill’s systems?  Are there any multiple factors for authentication or restrictions/protections?
All authentication secrets are stored either hashed or encrypted. Only the latest known-to-be-secure schemes are used. For hashing, we generally use SHA1-256; for encryption, we use AES256. Multi-factor authentication can be enabled against Hornbill authentication from our own 2FA functions or via your own security provider such as ADF\SAML.

## How is the separation between customer data enforced/controlled in infrastructure and/or logically?
The Hornbill Platform segments every customer's dataset into an *instance*. You can think of an instance as a data sandbox. Each instance gets a dedicated database and dedicated file storage. Data isolation is achieved at the lowest layers of our stack. For the database layer, each instance has a database, and while multiple databases sit on the same physical server, each database has access credentials specific only to the instance to which it belongs. For the filesystem (file attachment storage, etc), data is segregated based on the instance. The design of our application stack ensures that sessions are keyed to an instance using cryptographic techniques to make it impossible for one customer's dataset to be cross-contaminated with any other customers dataset.

## How are resources allocated within the Cloud/SaaS platform? Who/what gets priority? SLA?
Resources are allocated commensurate with the size of the instance (number of subscribed users) as well as by workload demand. Workload priority is based on ensuring that individual API calls complete within timings set based on the class of the API, and we adjust resources according to those rules. It is in Hornbill's commercial interests to always keep our service performant and available, and we consistently achieve well above our target of 99.95%. See [our service performance metrics](https://status.hornbill.com/).

## What are the different editions of Hornbill?
For detailed explanation of Hornbill editions, please visit [the documentation](/esp-fundamentals/about/hornbill-editions).

<!-- https://beta.hornbill.com/hornbill/post/urn:buzz:activity:15d3f6ed-7d01-46e9-af65-c4b6f6a0bb7e -->
<!-- https://docs.hornbill.com/hornbill-cloud/data-security-commitment -->

## Was Hornbill's architecture designed or reviewed by a qualified security architect?
While it is difficult to state in absolute terms what a qualified security architect is, Hornbill's technology stack and system design have been built over three decades by a team of professionals who bring many decades of combined experience and expertise --- designing, building, and operating complex cloud software and business applications that meet and often exceed continuously reviewed security needs.  Our systems are continuously monitored, reviewed, and tested against maintained and certified security standards including ISO27001 and ISO27018. We undertake penetration testing exercises and have all the features required for securing, monitoring, and auditing all aspects of the systems operation in relation to security concerns. We have operated a robust SaaS solution for over 15 years, with zero incidents of data loss or security breaches in that time, whilst consistently maintaining five-nines system availability.

## What is the MTTR for Outages?
The Mean Time to Recovery (MTTR) for outages, specifically referring to the service interruptions experienced by Hornbill, has been calculated to be 2 minutes and 45 seconds when averaged across all instances. This is less than 1 Minute for Enterprise instances which have higher resilience and shorter fallover times. 

For those interested in more detailed and real-time insights into Hornbill's service status, including the frequency and impact of outages, users can visit status.hornbill.com. This platform provides comprehensive data, historical performance, and updates regarding service availability, offering transparency and allowing users to stay informed about the operational status of Hornbill's services.

## Who is Hornbills DPO?
Hornbill, as mentioned, does not have a designated Data Protection Officer. This is because it does not meet the specific criteria outlined by GDPR that would necessitate the appointment of a DPO. However, we have appointed a senior member of the board in a similar role and they can be contacted via security-hornbill@live.hornbill.com


## Does the Application have a web application firewall in place?
Hornbill, the application leverages Cloudflare, a renowned service provider in the realm of web performance and security. Cloudflare is utilized by Hornbill to function as both a load balancer and a front-end cache. This dual role not only optimizes the distribution of incoming web traffic across multiple servers, enhancing the application's performance and reliability, but also helps in managing and reducing latency for end-users by caching content closer to their location.

Cloudflare's suite of services includes a robust web application firewall (WAF), which Hornbill has the option to employ as part of its security strategy. This WAF is designed to protect web applications by filtering and monitoring HTTP traffic between a web application and the Internet. It does so by enforcing security policies to block or filter out potentially harmful requests before they reach the application server.


## Does the Application have a real-time application protection in place?
Hornbill integrates a comprehensive suite of Security Information and Event Management (SIEM) technologies designed to monitor, detect, and respond to security threats as they occur. SIEM systems are pivotal in cybersecurity infrastructure as they provide real-time analysis of security alerts generated by network hardware and applications. This capability is essential in identifying suspicious activities that could indicate a security breach or an attempt to exploit vulnerabilities within the system.

These SIEM technologies collect, aggregate, and analyze log data from various sources across the IT environment, offering an overarching view of potential security threats. By utilizing advanced algorithms and machine learning, these systems can discern between normal and anomalous behaviors, thereby providing actionable insights and alerts to security teams. This enables them to take immediate action to mitigate any potential threats before they can cause harm.

Furthermore, Hornbill's approach to real-time application protection is likely enhanced by additional layers of security measures. These may include intrusion detection systems (IDS), intrusion prevention systems (IPS), and automated threat intelligence feeds. Such tools work in tandem to bolster the system's defenses, ensuring that any attempt to compromise the application is swiftly identified and neutralized.



## Can we delete records or users after a Number of Years?
Hornbil, offers a suite of tools specifically designed to facilitate data hygiene and compliance with data retention policies. These tools are highly versatile and can be configured to execute automated tasks according to a predetermined schedule, ensuring that data is managed efficiently.

The platform allows administrators to set up these tasks to target specific types of data, such as user accounts, service requests, or any other data entities within the system. This flexibility means that organizations can tailor their data management practices to suit their unique operational needs and compliance requirements. For instance, user data that is no longer needed after a certain period can be automatically deleted to free up system resources and reduce potential security risks. Similarly, old service requests that have been resolved and are no longer relevant can be archived or purged to streamline the database and improve overall system performance.

The scheduling capability of Hornbill’s tools ensures that these data management tasks can be performed during off-peak hours, minimizing disruption to daily operations. This automated approach not only saves time and reduces the workload on IT staff but also enhances the accuracy and reliability of data management processes. By systematically removing outdated or unnecessary data, organizations can maintain a clean and efficient database, ultimately optimizing their service delivery and ensuring compliance with data protection regulations such as GDPR or CCPA.


## Is Hornbill PSN-P compliant? and are the data centers PASF accredited (Police Assured Secure Facility)
Hornbill, is not PSN-P compliant. PSN-P certified, or its data centers Public Services Network Protect certified. 

However, while Hornbill may not have achieved PSN-P compliance, it is important to highlight that all of its data centers are subject to rigorous control measures. These data centers are governed by stringent security protocols that are designed to meet and often exceed the requirements set forth by PASF accreditation. PASF, or Police Assured Secure Facility, is a certification that ensures facilities maintain the highest standards of security, making them suitable for handling sensitive police and governmental data.

Although the data centers themselves are not officially PASF accredited, Hornbill's commitment to security is evident in the comprehensive measures they have implemented. These measures include advanced physical security, access control systems, robust cybersecurity frameworks, and constant monitoring to safeguard data against potential threats. These security practices ensure that Hornbill’s data centers provide a secure environment that aligns closely with the objectives of PASF accreditation, thereby offering a high level of assurance to its clients regarding the safety and confidentiality of their data.


## Can I request data restored fromm Backups, If I accidently delete something

Hornbill backups are primarily intended for disaster recovery (DR) purposes, not for correcting customer-initiated data deletions.

However, upon customer request, Hornbill can investigate the feasibility of restoring only the deleted content. This investigation may be chargeable at an hourly rate.

The complexity arises from the intricate relationships between different entities and the distributed nature of data across multiple tables.

Directly restoring only the deleted data is often impractical due to the following:

* Identifying "missing data" requires a full system restore on a separate database for comparison.
* Complex inter-entity relationships make selective restoration challenging.
* For example, if a customer deletes all call requests starting with "1234", identifying and restoring the affected data would involve:

* * Extracting all matching records from the primary table.
* * Identifying and restoring related data from over 30 associated tables.
* * Locating and restoring any related emails and their attachments.
* * This comprehensive process necessitates a thorough investigation to determine the most efficient and cost-effective recovery method.

Once the review has been performed we will advise if the restore or just the missing data is feasable or an entire restore to last backup point is required. If you choose you can also have an export of the identified data for manual or other non restorative methods. 


## What is the importance of the Instance Name in respect to provisioning your Hornbill Instance
The Instance Name is used in the URL used by your organisation to access your specific Hornbill instance, this needs to be memorable easily identifiable and unique to your organisation.

By way of example the Hornbill Public Demo instance which is available on our Corporate Website has the instance name Demo as such access to this is possible from the following URL https://live.hornbill.com/demo/

As part of the sign up process for you will be asked to provide an Instance Name which our Product Specialists will use to initiate the provisioning of your specific Hornbill instance.

The instance name should adhere to the following criteria:

* Must be unique and identifiable. As such requests for intance names such as itsupport, serivcedesk or help will not be accepted.
* Only contain letters and numbers (and must start with a letter)
* No special characters (&, +, =, etc.)
* Be no more than 45 characters long
* Any Hornbill controlled email addresses must also contain this InstanceName at the end, for example - support-InstanceName@live.hornbill.com


In the event an Instance Name is requested that has already been allocated you will be advised and an alternative will need to be provided.

Hornbill retains the right to reject an Instance Name if it is felt to be inappropriate.

Care should therefore be given when choosing an InstanceName to ensure that its easily memorable and reflects your organisation.



## Can we Change our InstanceName
It is possible should you wish to change your InstanceName at a later date, however the following must be considered.

* Change will be made and old InstanceName retired. There is no redirection from old to new.
* Any @live.hornbill.com email address will also be changed to include the new InstanceName. There is no redirection from old to new.
* Any not relative Hyperlinks contained within comments or calls may not function.
* Any not relative Hyperlinks contained within comments or calls may not function. (Note all Hornbill added links will be OK)
* Downtime is required. Normally this is around 30 minutes, however the more data you have the longer this takes.
* Any SSO profile may need to be updated.
* Any Push data imports may need to be reconfigured.
* BPMs should be checked to ensure they do not contain any hardcoded URLs
* Email templates should be checked to ensure they do not contain any hardcoded URLs (you might want to consider using the email template variable: {{instanceId}} )

Hornbill allows 1 change of InstanceName without cost, subsequent changes will be charged. It should be noted that InstanceNames are provided on first-come first-served basis and Hornbill retains the right to reject an Instance Name if it is felt to be inappropriate.

Although it is possible to undergo a Instance Name change without any professional services, we do recommend engaging with the team as they can then perform a full review of your system to highlight any of the above areas that may be of concern.


## What is the Account Authority, and what responsibilities does this person have?
The Account Authority is a named contact on record for your Hornbill Instance who has the authority to make commercial and strategic decisions on behalf of your organisation in relation to Hornbill, these responsibilities include and are not limited to:

* Accepting the Hornbill Solution at the end of a 30 Day Free Trial and initiating the subscription to the Hornbill Service.
* Increasing or decreasing the number of subscriptions to a particular Hornbill solution.
* Subscribing or Unsubscribing to a Hornbill application.
In essence this person is the overall sponsor of the Hornbill Solution within your organisation.

## What is the Primary Technical Contact, and what responsibilities does this person have?
Once the Switch On is complete, it will be necessary to have on record one or more support contacts. The primary contact will have the authority to raise questions or requests with Hornbill Support and will be required to liaise with the Hornbill Customer Success Team with regards to implementing solutions. They should also have the authority to make decisions regarding Cloud Service availability (in the unlikely event of our Cloud team needing to co-ordinate a downtime requirement). The contact should be trusted with Application Admin privileges.

They will also be required to approve the registration of additional support contacts. You may depending on your Success Plan add a number of additional supported contacts. Hornbill will only take support requests from known and pre registered contacts for your instance as part of our cloud security policies.

## What is the Secondary Technical Contact, and what responsibilities does this person have?
It is advisable to have a Secondary Technical Contact within your organization registered with Hornbill so as to allow this person to raise Application Support requests with the Hornbill Customer Success Team in addition to or in the place of your Primary Technical Contact should they be unavailable.

## What is the Data Security Officer, and what responsibilities does this person have?
If we have any data security issues that we need to raise with your organization, this contact would be our first port of call. This is typically the person in your organization responsible for your information security policies and practices, but it can be anyone you nominate. If you do not specify a contact point for this then we would default to communicating or sending notifications of such issues to the authoritative contact.
