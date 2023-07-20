---
layout: article-toc
---
# Data Polling
## Polling Data for System Integration
With some types of integrations, customers will have asked if they can poll our application data source in order to detect change conditions, in order to simulate change events to fire integrations for other systems. While this is simple to implement conceptually, it’s a very inefficient approach, especially when large data sets are concerned, and short polling times are needed to simulate near-real-time integrations. Dataset sizes in Hornbill are hugely variable and tend to grow over time so something that might work today may well become a problem in the future.

Hornbill is fundamentally a transactional system, the underlying application database prioritizes optimization for transactional performance over data query performance, in essence, the application database is not designed or optimized for large dataset queries. Through the user interface, datasets are always managed, and queries are paged and kept small in order to keep user responsiveness optimal.

When asked, we will always look at the merit of each request to perform this type of integration, but as a general rule we will not allow large dataset polling of our database, there is no direct database connection, and our APIs are generally restricted in the spirit of “fair use”, in our case fair use means, largely transactional integrations.

As an alternative to polling, the Hornbill platform provides a comprehensive set of integration capabilities that are available to customers, these are focused primarily on transactional events. Hornbill can call out to any other system via APIs through our iBridge and ITOM integration capabilities, while any third-party system can call into Hornbill via our comprehensive web service APIs. This is a far better, and far more supportable solution to systems integration.

General Guidelines for inbound (third party to Hornbill) and outbound (Hornbill to third-party) Integrations

* APIs are available and free to use for transactional inbound integration needs
* iBridge provides a comprehensive library of ready-made cloud integrations
* ITOM DevOps edition provides an environment for you to build behind-the-firewall or in-the-cloud custom outbound integrations.
* Webhooks for system integration

The above also applies to large data set extraction through reports\CSV or other methods including direct Query APIs. Hornbill provides alternate methods (Requested Data Dumps, Reporting ETL services, etc) that are better suited.

<!-- https://wiki.hornbill.com/index.php?title=FAQ:Hornbill_Data_Polling -->