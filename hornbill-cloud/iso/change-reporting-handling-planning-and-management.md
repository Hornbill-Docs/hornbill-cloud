---
layout: article-toc
---
# Change Reporting/Handling and Management
## Change management
Changes are logged in Hornbill Technologies’ own Hornbill instance. The originator obtains sufficient information to complete the Change Request form and obtains the Chief Technical Officer’s or Cloud Service Manager’s approval for the change, taking into account any technical considerations, the costs of the exercise, the potential benefits, etc.

Copies of all change requests are retained to provide an audit trail.

The Cloud service Manager is then responsible for reviewing and/or carrying out a risk assessment to identify potential risks, and their impacts and then to identify and cost the required controls in line with Hornbill Technologies’ risk management framework.

The Chief Technical Officer or Cloud service Manager in consultation with Managers is responsible then for authorizing the change to go ahead. No change implementation work is done until the change is agreed upon. Where required by the risk assessment, fallback procedures or a rollback strategy must be prepared.

If necessary, the testing plan can include a dry run of the change. Where the change is significant, a testing plan, complete with clear acceptance criteria [including business, technical, and load criteria] must be documented prior to commencing the change testing. The individual responsible for testing the change must be briefed.

Once the change is proved to be effective the Cloud service Manager authorizes its transfer to the operational environment, ensuring that business processes are not disturbed and that business continuity plans are updated if appropriate. Authorization may be granted by e-mail as appropriate which should be retained and appended to the relevant Change Request Form.

## Test, development, and operational facilities
All testing is conducted in a test environment that is configured for that specific test requirement. It is separated from operational facilities by logical means and requires a password for access, which is issued by the Cloud Team.

All testing for core platform changes is performed in Dev\BETA environments with https://wiki.hornbill.com/index.php/Continuous_Delivery being used to ensure problems are found\rectified before Live.

No data from the live environment is ever used for testing and all test data used by developers is pseudo-generated.

<!-- https://wiki.hornbill.com/index.php?title=ISO:Change_Reporting%5CHandling%5CPlanning_and_Management -->