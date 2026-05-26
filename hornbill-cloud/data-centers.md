---
layout: article-toc
---
# Data Centers
My security team have asked to know more about Hornbill's Data Centers, please can you advise?
All our data centers comply to SSAE16 Our data centers are SSAE (Statement on Standards for Attestation Engagements) 16 Type II and CSAE (Canadian Standard on Assurance Engagements) 3416 certified. Certified Tier 3 Data Center as well as ISO27001.

Who is responsible for delivery and management the Hornbill Cloud Service, is this outsourced?
Hornbill is solely responsible for the delivery of our service. We do not operate our own physical data centers, instead we take space in reputable data centers and run our own hardware, either our own assets or rented bare metal servers. So the servers, storage, networking and the entire software stack from the operating system up, are dedicated to - and operated by us directly.

What business continuity provisions are in place to ensure continuity of supply, of the product?
Hornbills SaaS platform has been designed so that it is portable between data centers, enabling Hornbill to easily transfer to another data center in the event of a contingency or capacity need. Although we prefer to deliver our cloud service on our own dedicated computing infrastructure, our solution is designed to easily spill-over into Amazon EC2 should we need to in an emergency, our data center regions mirror those of Amazon EC2 for this reason.

Every customer instance runs with a near real time replication of its data to a secondary data center in the same geo-location, this ensures that apart from our scheduled backup snapshots we *always* have two physical copies of our customers data to work with should any disaster strike in a single data center.

Our data centers have on-site diesel-powered generators and uninterruptible power systems (UPS), which deliver redundant power if a critical incident occurs. This ensures all operations are uninterrupted, and the dedicated servers remain online. The data center service team will regularly test that the infrastructure performs as designed in the event of an emergency.


## Data Centers and Facilitators
Depending on Geo Location your data will reside in 1 or more of our chosen data centers inside the Country or legal geographical grouping that covers your chosen country (For global companies you can choose which home country/legal entity your instance resides in). These are provided by 3 main companies depending on location with Amazon AWS being our defacto fail over for disaster recovery should it be required.

This allows us to achieve staggering levels of availability in any location around the globe. However, we will always ensure that these providers are fit for purpose and offer at least the same level of security we ourselves would offer. We achieve this by ensuring that all Data Centers conform to recognized international standards including ISO27001\SSAE16 amongst others.

All our data centers must be secured and physical security perimeters (e.g., fences, walls, barriers, guards, gates, electronic surveillance, physical authentication mechanisms, reception desks, and security patrols) shall be implemented to safeguard sensitive data and information systems. We also ensure that prior to any relocation or transfer of our hardware (Either Onsite or Offsite) that authorization is obtained (Our monitoring would detect and inform us of any unauthorized attempts). All facilities will only allowed approved persons entry and each request must be authorized separately. Segregation within data centers is physical usually by use of cages or server cabinets.

All data centers\facilitators have policies and procedures for the secure disposal of equipment. This includes a wiping solution or destruction process that renders recovery of information impossible. Any equipment including hard drives are destroyed once wiped rather than recirculated and documents\certificates confirming this provided should we not be present to witness the event.


### PEER1\Aptum
The highly secure and redundant IT infrastructure provides Hornbill with a remarkable data center platform upon which we deliver our cloud services.

Peer1\Aptum provide us with networking infrastructure and bare metal servers. We provide our own complete software stack and manage all of our PODs from a 24x7x365 network operations center based in the UK.

SSAE (Statement on Standards for Attestation Engagements) 16 Type II
CSAE (Canadian Standard on Assurance Engagements) 3416 certified
ISAE 3402 certifications
Data Centers include Portsmouth, Los Angeles, Dallas, Washington, New York, Toronto, London, Portsmouth, Amsterdam, Frankfurt, Paris, Singapore, Sydney, Mexico City and many more

### IOMART & RAPIDSWITCH
We co-locate our own hardware at RapidSwitch. We run our own servers, firewalls, and switches as well as the complete software stack, and manage these servers directly.

All IOMARTS\RAPIDSWITCH data centers hold the following certifications

`ISO 27001: 2013`<br>
`ISO 9001: 2015` <br>
`ISO 50001: 2011 Energy Management`<br>
`ISO 23301: 2012`<br>
`ISO 20000: 2011`<br>

Data Centers include London, Manchester, Maidenhead, Glasgow, Toronto, Buffalo, Chicago, Dallas, Dublin, Amsterdam, Frankfurt, Sydney, Singapore, Tokyo, Dubai and many more.

### Equinix
We co-locate our own hardware at Equinix Data centers (If your Primary DC is IOMART\Rapidswitch your Secondary will be Equinix and vice versa for redundancy). We run our own servers, firewalls, and switches as well as the complete software stack, and manage these servers directly.

All Equinix data centers hold the following certifications as a minimum.

OHSAS 18001
PCI-DSS
SSAE 16/ISAE 3402 SOC-1 Type II
ISO 5001
ISO 27001
ISO 9001
Equinix data centers exist in Paris, London, Tokyo, Washington, Shanghai, New York, Sydney, Houston, Melbourne, Frankfurt and many more locations.

### Amazon EC2
Unlike Peer1\Equinix\IOMART\RAPIDSWITCH, Amazon owns the servers and we rent CPU time\space. This means in the event of a problem at a given data center that can not be rectified we can switch to AWS at a moments notice. AWS operates 43 Availability Zones within 16 geographic regions around the world, with 11 more availability zones and 4 more Regions coming online soon.

<!-- https://wiki.hornbill.com/index.php?title=FAQ:Data_Centres#Datacenters_and_Facilitators -->
