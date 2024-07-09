---
layout: article-toc
---
# Operations
## Capacity management
Network utilization, disk utilization, and server load are monitored. This provides automatic alerts when pre-set thresholds are exceeded. The Chief Technical Officer is responsible for ensuring this monitoring is conducted and action is taken to resolve any issues.

We have hardware available for our expected growth of Hornbill and this is reviewed\increased every 3 months with the purchasing of additional hypervisors\rack space. If required, we can also create an instance or complete replica of the Hornbill infrastructure in AWS in record time meaning that capacity and scalability are never an issue. This scalability along with the underlying server code also removes all limitations for user increase as new servers can be added as demand increases.

Network utilization, disk utilization, and server load are monitored in real-time by a collection of over 1000 data points (CPU\RAM\HDD utilization for all services, etc) for use in graphing\realtime monitoring. These tools\charts\engines provide automatic alerts when pre-set thresholds are exceeded. The Chief Technical Officer is responsible for ensuring this monitoring is conducted and action is taken to resolve any issues.

## Monitoring
All Instances, Services, and Hardware are monitored from several locations around the world (Each monitor server acts as a backup to the primary and results compared). We check over 1000 different metrics per instance (and anything that an instance may require) every 5 minutes to ensure all is well. Any warning is logged and escalated to the Cloud Team.

Checks include (Not comprehensive list)

Performance (Pings, DNS Propagation, Response times from API, CPU Load, RAM Load, Disk IO, network Load, etc)
Hardware (Availability, Temperature, SMART, SNMP, etc)
Capacity (Disk Space, CPU, RAM, etc)
Availability (Ping, DNS Propagation, API Tests, Host controller checks, etc)
Security (Automated Log file reviews, Traffic review, Pattern analysis, etc)
IDS (Intrusion Detection, Suspicious or Malicious Traffic Analysis including, packet\bandwidth\source\traffic monitoring)
Data Leakage ( Packet\bandwidth\Source & Destination\traffic monitoring and Analysis. )
Backups (Sync checks, replication checks, Off instance checks, etc)
Sanity (Checks for Mail Queues, Expected load, etc).
SIEM (APIs\Resource Usage\Network Traffic and DB Access\Requests)

Hornbill also maintains a fingerprint for each instance for each hour of the day across different days for key metrics (APIs\Resource Usage\Network Traffic\DB Access\Count of Emails In\Out etc) which are compared with the live instance metrics every 15 minutes. This allows us to detect any abnormal patterns which may indicate internal issues, threats, security issues, misconfiguration or other strangeness near real-time. Anything outside of a standard deviation from normal for 1 or more of the key metrics for each fingerprint is subjected to further automatic review and the outcome of this will escalate under conditions to the Cloud Team. After review, this may be escalated to the instance contacts for clarification or notification of possible issues. In extreme circumstances (Either exceptional load, possible security issue, or similar) Hornbill will act to prevent harm to the instance or platform and the contact for instance informed of the action taken and the reason.

## Security Information and Event Management (SIEM)
We have a number of ways of monitoring Hornbill Instances to detect abnormal functions. 

### How SIEM Works 
We collect and store 100s of metrics every 15 seconds which gives us an understanding of what is normal for any instance and instances in general. Because people are creatures of habit which is further enforced by work patterns and routines we are able to see patterns in the data that lend themselves to statistical analysis. 

### API Count Example 
People generally do the same thing every day, they get up in the morning at the same time (the alarms set), they go to work at the same time (it's in their contract) and they perform the same actions at nearly the same time every day (First thing read your email, then read posts, then check BBC, then go for coffee, then process new calls, then off hold calls etc). The pattern repeats and because of this, we see in every instance a similar number of API calls per hour (within 1 standard deviation of normal) every day during the week and another pattern during the weekend.  This is further enhanced by the use of automation, and things like scheduled reports or scheduled jobs which also always happen at the same time. 

If we take these counts of API per hour for a given instance we see a pattern similar to the example below, and we can then look for anomalies in the data every hour when comparing to the previous 6 or 12 months for that hour.  Any change to people's work patterns may initially cause alerts but over a longer enough period these become the new normal. 

We can also look for daily, weekly, shift, and other patterns, and anything that is statistically significant (1 or more standard deviations from the normal ) is investigated. 
We perform this analysis every hour of every day on all instances and anything found gets flagged to the cloud team SIEM workspace for review.  A manual review is then used to try and understand the events and then any remaining concerns are escalated to the contacts for the given instance. 

We perform the same statistical analysis on load, database, data in/out, and other metrics as well as API count to have an understanding of what is "normal" and what is not. 
The below image shows an example of the patterns we look for (its compared data ), and what happens when an alert is generated.

![SIEM Example](/_books/hornbill-cloud/images/siem-example.png)

The above will allow us to spot issues due to misconfiguration, product issues (either defect or useability), or worse including security events, and escalate these to you as soon as possible.

## Backups
All databases are replicated in real-time to separate data centers and all files are replicated off-site within 15 minutes. These replicas are then backed up (individual secure archives encrypted with 1 time key) each evening and stored off-site within S3 for the retention period specified in contracts. The backups are taken without any interruption of services

Our 'Maximum Data Loss Time Period' or RPO is a maximum of 24 hours (or the time back to the last 23:00 backup). However, we aim for 15 minutes, as we replicate customer data at this frequency. Hornbill's RTO 'Recovery Time Objective' in the event Hornbill has to invoke its DR (Disaster Recovery) plan is defined as

Emergency response to assess the level of damage, decide whether to invoke the plan and at what level, notify staff, etc. (to be completed within 1 – 2 business hours of the disaster)

* Provision of an emergency level of service (within 4 business hours of the disaster)
* Restoration of key services (within 8 business hrs of the disaster)
* Recovery to business as normal. (within one week of the disaster)
  
The emergency level of service is to ensure our customers and their customers can use the Hornbill Services and applications with minimal disruption. To this end all Applications and databases will be restored however file attachments (Associated with emails, workspaces, Document Manager, or requests) might not be available, and search functionality will be limited.

Restoration of Key services will be to provide the customer with a fully working system and no difference from what they had before the DR plan was activated. All Applications, Databases, File Attachments, and functionality restored.

Recovery to business as Normal would only ever be needed should a true Disaster occur. This would include the total loss of 1 or more data centers AND Hornbill offices at the same time. The Recovery to business as Normal would ensure that all Hornbill services (both customer facing and internal) were fully restored).

In order to achieve the RPO and RTO targets we perform file replication of customer instances (and all servers) to off-site location at least every 15 minutes as well as real-time database replication (again off-site). Both actions are monitored and any delay over 1 hour is flagged as critical. Nightly backups are then taken from the above locations and stored locally and offsite (3rd location).

Therefore, should a failure exist on Primary hardware we can recover from replicated files (Max 15mins) or in complete disaster tertiary 3rd backups

Backups are checked for integrity automatically at the time of taking, upload to S3, and at different levels either Weekly or Monthly.

It is noted that for GDPR removal requests any deletion of data from an instance will not be deleted from any backups and will be removed via the cycling of the backup (up to 90 days.). On any restore, Hornbill will then re-remove the requested records as per the Service Manager incident request. The customer can request to have all backups deleted (On the understanding that no historic backups will be restorable prior to this) that contain the removal request data.

## Access
Access to any system is restricted. All default passwords are changed. All Logins to systems processing customer data will automatically send a report to the Hornbill Login Workspace (allows anyone in the company to highlight or ask questions on why access and provides transparency) and raises a request. This Login must then be associated with a given service manager request or Hornbill workspace post to ensure a valid reason exists to log in. These Logins are then audited by the Security manager to ensure no unauthorized access was performed.

Passwords on all systems are changed on leave or schedule.

Backups are restored (and therefore restore process tested) nightly to ZIP before being pushed to an offsite location and a random backup restore is performed on a scheduled basis to ensure that backups are correct\valid.

## Temporary Files
All temporary files on systems that process customer data are deleted after 24 hours. All other systems are set to clear temp folders on reboot. These are purged at 0100 on a nightly basis from all nodes

## Customer Access to Logs
Customers can access their own logs via the Admin portal, these logs are restricted to their instance and any shared logs (Such as Web front end, DataService logs etc) are not available. This ensures that the cloud service customer can only access records that relate to that cloud service customer’s activities and cannot access any log records which relate to the activities of other cloud service customers. Customer accessible logs are available for the current day (Note that this is different to Audit Logs, such as security logs which are available for 6 months) via the portal and on request for 2 months from Hornbill (requests should be submitted to data.processor-hornbill@live.hornbill.com ) by the nominated contacts for a given instance (Technical or Data Security).

## Customer Access to Audit and Access Logs.
The above logs are more aligned to identifying issues or misconfiguration in processes or other aspects of the application rather than Audit\Security or Access. The logs used for Audit\Security or Access are typically far larger based on the sheer volume of data and are kept for 7 days. These should therefore be exported by the customer (via Scheduled report or other integration) to a repository of their choice.

The logs

Primary Security Log - Contains all Login Requests and the source IP, timestamp, target (portal, live, admin, etc), result of the action, and Unique ID.
Primary Audit Log - Contains all pages\entities accessed and the UniqueID of actor and timestamp of action.
Application Audit Log - Each application has its own Log table containing a timestamp, action (Insert, Update, Delete records, etc), Unique ID (linked to above), the result of the action, and previous and subsequent values. See each application's documentation for a full list of Audited actions.

## Software
Only approved Software may be installed on all desktops\servers utilized by Hornbill. The source for which is stored within a central repository to ensure that even in a disaster we can install as required. All software utilized by Hornbill is reviewed on a scheduled basis.

Software is managed\deployed through central systems (Anisble\Hornbill Tools\Hornbill ITOM) to ensure correct deployment and configuration.

All software is hardened in line with Vendor, Industry, and Hornbill's own policies and standards. This includes, only required software\services per machine, locked down ports\individual users and service accounts, etc. All hardening is confirmed via monitoring and any changes would automatically escalate and automatically reverted within 5 minutes of any unsanctioned change.

## Hardware
Only hardware provided by the IT team and obtained via existing approved vendors may be used to access the management or customer networks. All Clocks are synchronized with NTP and checked to be within 1 minute of primary servers. All default passwords changed. All hardening is in line with Vendor, Industry, and Hornbill's own policy and standards. All hardening is confirmed via monitoring and any changes would automatically escalate and automatically reverted within 5 minutes of any unsanctioned change.

<!-- https://wiki.hornbill.com/index.php?title=ISO:Operations -->
