---
layout: article-toc
---
# Business Continuity
Hornbills configuration of servers\services has been planned to ensure that there is no single point of failure, all services have fail over servers or spare capacity.

## Business Continuity and Disaster Recovery plan
Hornbill are committed to providing customers with access to their subscribed services and data even in the event of a emergency or disaster. Our plan is designed so that in the worst possible case customers will be without access to instances for the minimum time possible whilst a full restore is carried out to a secondary data center.

In the event of a disaster or high impact issue the Cloud team have the option to invoke the Emergency plan. Once started this ensures additional resources are provided to the cloud team and non-critical work is suspended.

The plan is tested against 2 main scenarios at least once every year to ensure that in the case of Loss of Hornbill offices or Loss of Data Center we are able to continue to provide all services as expected.

Testing is performed remotely and its objectives are to show that we can continue to provide all services to existing customer, recreate the contents of 1 or more data centers in time specified in our SLAs and begin to provide all back end services used by Hornbill offices by the end of 1 working day.

Our 'Maximum Data Loss Time Period' or RPO is a maximum of 24 hours (or the time back to the last 23:00 backup). However, we aim for 15 minutes, as we replicate customer data at this frequency. Hornbill's RTO 'Recovery Time Objective' in the event Hornbill has to invoke its DR (Disaster Recovery) plan is defined as

Emergency response to assess the level of damage, decide whether to invoke the plan and at what level, notify staff, etc. (to be completed within 1 – 2 business hours of the disaster)

* Provision of an emergency level of service (within 4 business hours of the disaster)
* Restoration of key services (within 8 business hrs of the disaster)
* Recovery to business as normal. (within one week of the disaster)

  
The emergency level of service is to ensure our customers and their customers can use the Hornbill Services and applications with minimal disruption. To this end all Applications and databases will be restored however file attachments (Associated with emails, workspaces, Document Manager, or requests) might not be available, and search functionality will be limited.

Restoration of Key services will be to provide the customer with a fully working system and no difference from what they had before the DR plan was activated. All Applications, Databases, File Attachments, and functionality restored.

Recovery to business as Normal would only ever be needed should a true Disaster occur. This would include the total loss of 1 or more data centers AND Hornbill offices at the same time. The Recovery to business as Normal would ensure that all Hornbill services (both customer facing and internal) were fully restored).

Any outcomes\failings in the tests are noted and addressed within 1 month of the exercise and if necessary a new test scheduled.

A redacted version of the DR Plan is available on request.

## Backups
All instances are replicated real time to a central server located within the same geographical location as the live instance and then nightly backups of these are taken and stored within S3 (again within same geographical location) every evening. The backup process is monitored\tested to ensure successful upload automatically and a manual restore of a random instance performed every month to ensure data integrity. In the event of the emergency plan being activated and needing to restore, we will first attempt to use the live replication and should that be unavailable (Unlikely) we would revert to the last nightly backup.


See also FAQ:Availability & Scheduled Maintenance

<!-- https://wiki.hornbill.com/index.php?title=ISO:Business_Continuity_and_Disaster_Recovery -->
