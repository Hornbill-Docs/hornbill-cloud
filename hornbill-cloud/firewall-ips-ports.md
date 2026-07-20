---
layout: article-toc
---
# Firewall IPs and Ports
Hornbill will send data from the below IPs\Ports. We recommend that you open all the below IPS to your chosen integration points on the required ports. These IPs are static and we will advise of any change at least 30 days in advance

## SMTP Traffic
Hornbill will send SMTP Traffic on Port 25 from
|Region|IP #1|IP #2|
|-|-|-|
|Europe|87.117.243.10|212.71.225.67|
|North America|69.174.249.200|64.34.188.200|

## POP3/IMAP
Hornbill will connect via POP3/IMAP On Ports 110, 143, 993, 995
|Region|IP #1|IP #2|
|-|-|-|
|Europe|87.117.243.10|212.71.225.20|
|North America|207.198.105.122|64.34.188.194|

## HTTP/HTTPS/WSS
Hornbill will communicate using HTTP/HTTPS/WSS on Port 80 or 443 via

|Region|IP #1|IP #2|
|-|-|-|
|Europe|87.117.243.10|212.71.225.20|
|North America|207.198.105.122|64.34.188.194|

## Cloudflare
Hornbill uses Cloudflare as a front end to provide geographical caching of static assets, all static content (NOT customer data) requests go via Cloudflare for load balancing, threat mitigation, and prevention. This front end also provides initial SSL certs (via sni.cloudflaressl.com) again for static (NON customer) assets. The list of Cloudflare resolved domains is below 

* `login.hornbill.com`
* `live.hornbill.com`
* `customer.hornbill.com`


All other traffic (Customer data) is via the below endpoints.

Hornbills API Endpoints depend on your geographical location and will be listed in your initial connection response, served over HTTP\S from the IPs mentioned above. These should also be whitelisted for HTTPS\WSS on port 443

* `lon-p01-api.hornbill.com`
* `lax-p01-api.hornbill.com`
* `wsh-p01-api.hornbill.com`
* `mdh-p01-api.hornbill.com`
* `hhq-p02-api.hornbill.com`

Hornbill also makes use of a number of URLs that should be whitelisted, these are

* `login.hornbill.com`
* `live.hornbill.com`
* `customer.hornbill.com`
* `files.hornbill.com`
* `files.hornbill.co`
* `cdn.hornbill.com`

Hornbill's Data Import Tools will also need to connect to files.hornbill.com and files.hornbill.co

<!-- https://wiki.hornbill.com/index.php?title=Hornbill_Cloud_and_Platform -->
