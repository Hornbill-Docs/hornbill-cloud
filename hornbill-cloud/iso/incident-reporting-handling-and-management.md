---
layout: article-toc
---
# Incident Reporting, Handling, and Management
Information Security weaknesses, events, and incidents are reported immediately after they are seen or experienced to the ISM, on form REC 13.1A which is kept on the Hornbill Technologies network. The person making the report will email a copy of the completed form to the Information Security Manager (ISM) and the Cloud Support Team. The e-mail will be flagged ‘Urgent’, and where possible will be preceded by a telephone call to the Information Security Manager (ISM). All reports should also be followed up by a telephone call to the Information Security Manager (ISM).

All Information Security weaknesses, events, and incidents are, immediately upon receipt, assessed and categorized. As part of closing out the event or incident, this assessment is documented. Initially, there are four categories: Events, weaknesses, incidents, and unknowns: -

‘Events’ are occurrences that, after analysis, have no or very minor importance for Information Security;

‘Weaknesses’ are vulnerabilities that, after analysis, clearly exist as significant weaknesses compromising Information Security;

‘Incidents’ are occurrences of events (or series of events) that have a significant probability of compromising Hornbill Technologies’ Information Security;

‘Unknowns’ are those reported events or weaknesses that, after initial analysis, are still not capable of allocation to one of the four categories.

The ‘unknowns’ are subject to further analysis to allocate them to one of the other three categories as soon as possible.

The Information Security Manager (ISM) is responsible for closing out the incident. This includes any reports to external authorities, initiating disciplinary action as appropriate by referring the incident to the Information Security Manager; planning and implementing preventative action to avoid any further recurrence, initiating any action for compensation from software, service, or outsourcing suppliers by referring the incident to the Information Security Manager, and communicating with those affected by or involved in the incident about returning to normal working and any other issues.


## Notification
Notifications of service provision incidents (Not software\Application) affecting more than 1 instance will be available via the Hornbill Cloud Twitter account (Customers are advised to follow this), our status page, and our blog (Blog will provide further details and full write-up once the incident is over).

Primary, Secondary, and Authoritative contacts will be notified by email of any ongoing incident that lasts longer than 15 minutes with status updates every 30 minutes should the incident continue.

<!-- https://wiki.hornbill.com/index.php?title=ISO:Incident_Reporting%5CHandling_and_Management -->


## Hornbill Escalation Levels for Controlling Unexpected or Harmful Actions

Hornbill employs a multi-tiered approach to address and mitigate unexpected or harmful actions within its systems. This involves a series of escalating actions, each with increasing severity, designed to control the situation while minimizing disruption to both the affected instance and other customers. Nominated contacts will be promptly informed of any action taken at each level.

The time intervals between escalation levels are dynamic and depend on factors such as:

* Severity of the event: How critical is the issue? Does it pose an immediate threat to system stability or data integrity?
* Potential impact: What is the likelihood of the event causing widespread issues for other customers, beyond the immediate target instance?


Key Principles:

* Proactive Monitoring: Continuous monitoring through SIEM (Security Information and Event Management) and load alerts plays a crucial role in early detection of anomalies.
* Customer Collaboration: Hornbill prioritizes collaboration with customers at every stage of the escalation process to minimize impact and ensure a coordinated response.

Sample Escalation Levels:

Level 0: Notification

Triggers: SIEM alerts, load alerts, performance issues, data integrity concerns.

Actions:
* Initial investigation and assessment of the situation.
* Potential notification to the customer.


Level 1: Temporary Instance Suspension (Short-Term)

Triggers: Persistent performance issues, resource exhaustion.

Actions:
* Temporary suspension of the instance for a brief period (typically 5-10 minutes).
* Resetting the instance load to alleviate immediate pressure.
* Limiting resource consumption (CPU, query timeouts) to prevent further escalation.


Level 2: Temporary Instance Suspension (Extended)

Triggers: Continued resource exhaustion, potential for wider system impact.

Actions:
* Extended instance suspension (up to 15 minutes) with forced user logout.
* Further reduction of resource limits.
* Simple data modifications (e.g., adjusting auto-responder rules).


Level 3: Direct Data Modification and Resource Restriction

Triggers: Continued instability, potential for data corruption or unauthorized access.

 Actions:
* Direct data modifications (e.g., blocking user accounts, removing sensitive keys).
* Prevention of certain actions (e.g., running reports, accessing specific dashboards).
* Minimizing resource allocation to the instance.


Level 4: Extended Instance Suspension

Triggers: Unresolved issues despite previous actions, significant risk to system stability.

Actions:
* Prolonged instance suspension (up to 1 hour) to enforce corrective actions.
* Continued collaboration with the customer to identify and resolve the root cause.


Important Notes:

This is a sample escalation plan and may be adjusted based on specific circumstances and customer agreements. Enterprise customers have a less punative set of actions and greater resource allocation and tenant isolation. 

Hornbill reserves the right to take necessary actions to protect its systems and the interests of all its customers.

Regular communication and transparency with customers are essential throughout the escalation process.
