---
layout: article-toc
---
# Business Continuity
Hornbills configuration of servers\services has been planned to ensure that their is no single point of failure, all services have fail over servers or spare capacity.

## Business Continuity and Disaster Recovery plan
Hornbill are committed to providing customers with access to their subscribed services and data even in the event of a emergency or disaster. Our plan is designed so that in the worst possible case customers will be without access to instances for the minimum time possible whilst a full restore is carried out to a secondary data center.

In the event of a disaster or high impact issue the Cloud team have the option to invoke the Emergency plan. Once started this ensures additional resources are provided to the cloud team and non-critical work is suspended.

The plan is tested against 2 main scenarios at least once every year to ensure that in the case of Loss of Hornbill offices or Loss of Data Center we are able to continue to provide all services as expected.

Testing is performed remotely and its objectives are to show that we can continue to provide all services to existing customer, recreate the contents of 1 or more data centers in time specified in our SLAs and begin to provide all back end services used by Hornbill offices by the end of 1 working day.

Any outcomes\failings in the tests are noted and addressed within 1 month of the exercise and if necessary a new test scheduled.

A redacted version of the DR Plan is available on request.

## Backups
All instances are replicated real time to a central server located within the same geographical location as the live instance and then nightly backups of these are taken and stored within S3 (again within same geographical location) every evening. The backup process is monitored\tested to ensure successful upload automatically and a manual restore of a random instance performed every month to ensure data integrity. In the event of the emergency plan being activated and needing to restore, we will first attempt to use the live replication and should that be unavailable (Unlikely) we would revert to the last nightly backup.


See also FAQ:Availability & Scheduled Maintenance


## Epidemic or Pandemic
As part of our DR and Business continuity process, Hornbill already has a plan in place for Epidemics\Pandemics which is reviewed annually and when any new threat is detected. Covid-19 has been detected as a risk, however our exposure to this pandemic is relatively limited.

As a cloud-based company we are fully prepared for all our staff to be able to work remotely. Following Government guidelines issued on 16/03/20, all staff are working remotely from home as advised. This has been completed with no impact to existing customer services.

We have also received confirmation from all our data centers that they are also able to manage any risks associated with Covid-19 and do not expect services to be impacted.

<!-- https://wiki.hornbill.com/index.php?title=ISO:Business_Continuity_and_Disaster_Recovery -->