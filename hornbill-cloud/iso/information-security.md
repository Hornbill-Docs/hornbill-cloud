---
layout: article-toc
---
# Information Security
The Board of Directors and senior management of Hornbill Ltd (Hornbill) are committed to preserving the confidentiality, integrity, and availability of all physical and information assets owned and controlled by the company. Hornbill is committed to implementing a Secure Operating Model structured and conformant with the internationally recognized standard for an Information Security Management System (ISMS) ISO/IEC 27001:2013.

Information is only accessible to those authorized to access it and therefore preventing both deliberate and accidental unauthorized access to Hornbill’s information and proprietary knowledge and its systems including networks, websites, and associated software applications.

This includes safeguarding the accuracy and completeness of information and processing methods and therefore requires preventing deliberate or accidental, partial or complete, destruction or unauthorized modification, of either physical assets or electronic data. The information and associated assets should be accessible to authorized users when required, and therefore be physically secure. Internal and external networks must be resilient and Hornbill must be able to detect and respond rapidly to incidents (such as viruses and other malware) that threaten the continued availability of assets, systems, and information.

Senior management, full and part-time employees, sub-contractors, project consultants and any other external parties have, and will be made aware of, their responsibilities to preserve information security, to report security breaches, and to act in accordance with the requirements of the Hornbill’s ISMS. The consequences of security policy violations are described in Hornbill’s disciplinary processes contained within the HR policy. All will receive information security awareness training and specialist employees will receive appropriately focused training as required to meet Hornbill’s business, contractual, and regulatory requirements and obligations.

Hornbill ensures that its servers and operating systems are virus free at all times. However, our platform provides the ability for customers to upload content to our service storage in normal usage. Content is typically file(s) attached to e-mails, requests and knowledge documents, or images posted to comments and posts in our activity streams. This content is uploaded in an encoded format. 

 Hornbill does not perform virus checks on uploaded content, or perform any other content consistency checking; regardless of file type, any image or file is treated as a passive block of data bytes, we do not process this data in any way. The onus is on the customer to virus check files before they are uploaded, this is commonplace on may services that allow content uploads. The Hornbill solution protects itsself from potentially unsafe content by simply ensuring that any content uploaded to the instance is not processed in any way and stored in a format that does not allow execution on our servers. In addition to this, each customer instance runs in its own data sandbox which guarantees that it’s not possible to cross-pollinate data between customer instances, making it impossible for one customer uploaded content to affect any other customer instance

## Minimization
Only data that must be collected and stored SHOULD be collected and stored. The set of data should be the minimum required to achieve the goal. The Data security officer and team leads will be responsible for ensuring that any collected data is minimal. Any concerns or queries must be directed to the data security officers and a review of stored data conducted. All marketing exercises that involve the collection of data MUST be approved by the Marketing systems manager who will ensure that all data is the absolute minimum required, compliant with the required laws, and 100% OptIn with express consent obtained.

## Anonymization
Any data collected and processed for analytical reasons must be anonymized. The level of anonymization is per node\instance or service. No lower than service is permitted. Any data collected for security or Error detection (Log files) are not required to be anonymized before any processing but only the minimum used\made available for review, however, should the same data be used for any other purposes then it must be scrubbed.


## Statistics\Metrics\Measures
All data collected and processed for statistics, monitoring, and metrics must be anonymized. The level of anonymization is on a per node, instance, service, or API basis. No user should be able to be identified. Only counts or other integer values may be collected.

This means that we may collect, for example, the number of times a given API is used in a given time period or the time it takes for the API to complete. However, we will not have access to the data that was sent or received through the API request.

<!-- https://wiki.hornbill.com/index.php?title=ISO:Information_Security -->
