---
layout: article-toc
---
# Access Control
Access to any data\services provided by Hornbill is tightly controlled via a number of methods below.

## User Access Management
The ISMS Manager is responsible for allocating and authorizing user access rights in conformity with the policy. Changes in access rights are authorized by Line Manager and approved by the Chief Technical Officer or Cloud Team Lead.

There is a formal user registration and de-registration process maintained by the IT Manger.

The organization provides users with appropriate training and awareness.

The available access privileges for each of the organization’s operating systems, applications and other systems are identified and documented.

Privileges are allocated on a need-to-use and event-by-event basis; the request for allocation of a privilege is initiated in an e-mail from the user concerned to their Line Manager

The ISMS Manager logs all privileges authorized and allocated and checks on a regular basis that they have been de-activated as specified in the original request.

Checks include a check to ensure that unauthorized privileges have not been obtained.

## Password management
The allocation of passwords is formally controlled. Users are initially issued with a unique temporary network password which they are forced to change at first logon. Passwords must be changed every 3 months or when required by the ISMS Manager or if there has been a suspected breach or compromise.

Re-use of passwords is prohibited for 3 subsequent attempts as a minimum and minimum length of eight-character alphanumeric passwords are required using at least one capital letter and one numeral. Special characters are encouraged.

The default passwords on all new equipment are changed to conform to the organisation’s password requirements before the equipment is brought into service. Linux passwords are controlled by a central puppet server. This allows for automated creation and removal of user accounts.

All passwords are stored in 1 way HASH where possible and for those that need to be decrypted (ie POP3 password) a strong encryption algorithm is used (As per Cryptography controls document)

Review of access rights
To maintain effective control over access to data information services, user access rights are reviewed upon change.

## User Responsibilities
Passwords are not shared and are kept confidential by the user. Users must not write passwords down.

Where appropriate, paper and computer media is stored in suitable locked cabinets when not in use.

Restricted or Confidential business information is locked away when not required.

Laptops and printers are not left logged on when unattended and are protected by key locks, passwords or other controls when not in use.

All information, especially Confidential or Restricted information, when printed, is cleared from printers immediately.

Laptops are protected by key locks, passwords, screen savers or equivalent controls when not in use. Laptops have a screen saver enabled after 10 minutes inactivity.

Any workstations used in public areas have password-locked screen savers enabled to activate after 10 minutes of inactivity.

## Secure log-on
The screen displays no system or application identifiers until the network logon has been successfully completed.

The screen provides no help messages during the logon procedure.

The system validates the logon data only on completion of input and then, if there is an error, the system requires the user to try again.

The logon procedure limits the number of unsuccessful attempts allowed to three (and unsuccessful attempts are automatically recorded) and automatically enforces a time delay before further attempts are allowed.

Password characters are hidden by symbols.

Users are required to log out of sessions when they are finished.

## Network Access Control
Authorized users with permissions for devices or services, which they are given, shall access only those devices and services.

Authorized representatives shall access network equipments only. Network devices should not be enabled by default. Remote access is provided by a secure Virtual Private Network connection to the office.

A firewall is in place and controlled by the network team who ensure that only controlled ports are in use.

The organization monitors its network to ensure that, if any unwanted service or port is identified, appropriate steps are taken to apply appropriate controls.

## User authentication for external connections
Remote users log onto the network using VPN and remote authentication. The remote equipment is registered by the IT department. All remote Users undergo a Security and Remote working assessment ensuring that they remote environment is inline with the ISMS policies and practices. This is repeated every 12 months.


Remote diagnostic and configuration port protection Ports are locked down and only open only as required. Ports are protected by fire wall settings.


User identification and Users have unique identifiers and password as defined under user registration and in line with the Access Control policy.

Password management This is managed in accordance with sections above.

Use of system utilities Staff are experienced and knowledgeable and do not download and install system utilities unless such a utility will benefit the company.

Session time out Sessions locked out after 10 minutes inactivity Remote laptops using VPN are subject to same lockout after 10 minutes inactivity.

## Information access restriction
Restrictions to access to information is made in line with the Access Control policy and privilege management


## Segregation in Networks, Network Connection and Network Routing control
The network is segregated. This details the interconnectivity of the network and shows the relevant firewalls and routing. Configuration of firewalls and routers are retained securely so that in the event of a problem the units can be restored to correct functionality as soon as possible.

Inter-network connections are set in line with the Access Control Policy.

Routing of electronic messages is automatically achieved by using appropriate network protocols and automatic identification of equipment in the network using computer name identification.

## Clear Desk and Clear Screen policy
Users are required to ensure that no confidential or restricted information (in paper or removable storage media format) is left on desks or environs, or left in or near reproduction equipment (photocopiers, fax machines, scanners) when they are not in attendance and ensure that such information is secured in line with the Organization’s security requirements.

Users are required to ensure that no one is able to access their workstation when they are not in attendance and that a password protected screensaver operates within ten minutes of no activity or which they activate when they leave their workstation unattended.

Staff are required to terminate active computer sessions when they have finished them and to logoff (i.e. not simply turn off the computer screen) whenever they are finished working.

Staff must not connect personal storage media or MP3 players to the company network nor use digital cameras and personal mobile phones with photographic capability in the office without permission.

Staff may only use the Organization’s reproductive equipment (photocopiers, fax machines, scanners) for proper Organizational purposes and they ensure that they use facilities that are appropriate for the classification level of any information with which they are dealing.


## Monitoring
As well as the above instances\servers are monitored and configured to report logins, unusual access and\or unexpected data transfers, with all access to customer nodes logging calls that must be reviewed\associated with change request.

All logs are reviewed (automatically) daily to report any warnings or concerns and actions taken to address any concerns (For example, any port scanner or other bot probing would be blocked from all access). Instances are also monitored real time for access, anything falling outside of expected parameters will be logged as critical.

## Logs
All logs are stored for a minimum of 30 days upto a maximum of 2 years depending on system. This includes all Windows, Door Access, Linux, Application and Server logs. All Logs are continuously reviewed for either security or system errors and action taken when necessary.

<!-- https://wiki.hornbill.com/index.php?title=ISO:Access_Control -->