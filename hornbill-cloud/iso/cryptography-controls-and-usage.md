---
layout: article-toc
---
# Cryptography Controls and Usage
Your data and its security are as important to Hornbill as it is to you and we therefore encrypt all data in transit and at rest using a minimum of 256 bit.

All cryptographic tools used are sourced from legitimate sources and thus compliant with all relevant UK regulations related to cryptography. All encryption techniques utilize a minimum of AES 256-bit encryption and longer where possible.

All Hornbill controlled keys (SSH, Access, DB Encryption, DISK Encryption, Instance Encryption) are unique and randomly generated as required. Each key is then stored in a central password encrypted file that only permitted members of the cloud team can access (Access to each set of keys depending on roles). All keys are regenerated whenever a team member leaves the team or changes roles which affects access. All keys are valid for a maximum of 2 years before needing to be regenerated at which time the encryption technique used will be re-evaluated to confirm that this is still appropriate.

For external transport, we support and recommend secure protocols when providing integration (for example POP3S\IMAPS)and all web applications are served over HTTPS (All checked weekly via SSL Labs and others to ensure no known vulnerabilities)

A record of all encrypted data is kept and the encryption used is reviewed regularly to ensure that it is still fit for purpose.

All physical media that leaves Hornbill controlled sites is encrypted and records are kept detailing sender, Recipient, proof of receipt, encryption used, and dates.

## Internal Policy
All Disks, Laptops, removable hard drives, and USB memory devices are encrypted in line with the above conditions. All traffic that leaves the cloud network must be encrypted. All customer data stored at rest (DB\File Backups etc) must be contained within the encrypted volume and any data pushed to off-site backups must be encrypted in transit and at rest on target.

<!-- https://wiki.hornbill.com/index.php?title=ISO:Cryptography_Controls_and_Usage -->