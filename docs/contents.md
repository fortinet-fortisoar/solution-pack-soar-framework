| [Home](../README.md) |
|----------------------|

# Contents

This section lists the various contents of the SOAR Framework Solution Pack.

## Connector List

SOAR framework includes the following connectors:

| Connector Names          | Description                                                                                                                                                                                                                      |
|--------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Exchange                 | This connector provides a robust, platform-independent, and simple interface for communicating with Microsoft Exchange 2007-2016 Server or Office 365 using Exchange Web Services (EWS).                                         |
| File Content Extraction  | The connector is used to extract content, metadata and artifacts from over 1500 file types such as MS Office, PDF, etc.                                                                                                          |
| Fortinet FortiClient EMS | This connector provides operations related to quarantine/unquarantine endpoints, get endpoint details, and is a security management solution that enables scalable and centralized management of multiple endpoints (computers). |
| Fortinet FortiEDR        | This connector facilitates the automated operations related to events, forensics, and collectors.                                                                                                                                |
| Fortinet FortiGate       | Fortinet FortiGate enterprise firewall provides high performance, consolidated advanced security and granular visibility for broad protection across the entire digital attack surface.                                          |
| VirusTotal               | This connector facilitates automated operations such as scanning and analyzing suspicious files and URLs and retrieving reports from VirusTotal for files, IP addresses, and domains.                                            |
| Whois RDAP               | Whois RDAP is a service that enables you to retrieve information about the location of IP addresses, servers, or websites. You can find out the owner of the Internet resource and their contact details.                        |


## Modules

The SOAR framework includes the following modules:

| Modules        | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Alerts         | Alerts are primary actionable data elements that we obtain through a periodic ingestion process. We extract data through multiple channels like emails, SIEM platforms, or EDR platforms to create alerts. Once we have alerts, multiple playbooks are launched to extract and enrich the indicators.<br/><br/>To enhance or extend this default schema, refer to section [Extending Default Alert Schema](./extending-default-alert-schema.md).                                                                                                                           |
| Announcements  | The announcements module helps notify users who are a part of a war room.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Assets         | Assets represent a unique piece of hardware and any information known about that hardware, such as MAC address, hostname, or IP address. Assets preferably have a unique identifier. The assets module helps add devices within FortiSOAR for use by the SOC team. Computers typically represent the assets of your organization.                                                                                                                                                                                                                                          |
| Campaigns      | Campaigns are a collection of cases relatable to a single threat actor. Many times, disparate cases are connected attempts of a malicious attacker attempting to probe and gain access to a network.                                                                                                                                                                                                                                                                                                                                                                       |
| Cases          | Cases are confirmed alerts that negatively affect the confidentiality, integrity, and availability of an organization. Cases represent a collection of information discovered during a case Response investigation. Cases are triggered based on the suspicion or confirmation of a security breach.                                                                                                                                                                                                                                                                       |
| Communications | It helps users to communicate with external entities like tenant contacts, and other SOC teams, using email, instant messaging (IM), etc. from within an alert generated in FortiSOAR. For this purpose, it uses IMAP and Exchange connectors.                                                                                                                                                                                                                                                                                                                             |
| Events         | Events consist of records that contain machine-level information about activity that triggered a specific alert.                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Identities     | Identity records are user information which can be mapped to indicators of *type* `user` and act as a repository for alerts related to users.                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Indicators     | **Indicators of compromise** (IOCs) serve as evidence of probable intrusions on a host system or network. These artifacts help personnel at a Security Operations Center (SOC) to detect intrusion attempts or other malicious activities. IOCs help better analyze a particular malware's techniques and behaviors and provide actionable threat intelligence to further improve an organization's case response strategies.<br/><br/>Some of this evidence of potential breach is found on event logs and timestamped entries in the system, applications, and services. |
| War Rooms      | War Rooms in FortiSOAR is a collaborative space that enables SOC teams to mitigate a critical cyber threat scenario or campaign. FortiSOAR makes it easy for analysts to quickly and easily provision a War Room that allows participation of all stakeholders to analyze and collaborate to quickly mitigate the threat and restore the services. For more information, see the War Rooms chapter.                                                                                                                                                                        |

## Rules

Rules provide a framework to define a condition that generates notifications.

The SOAR Framework includes the following rules:

- Alert > Notify Creation - It sends a notification, via email, whenever an alert is **created**.
- Alert > Notify Updates - It sends a notification, via email, whenever an alert is **updated**.
- Case > Notify Creation - It sends a notification, via email, whenever a case is **created**.
- Case > Notify Updates - It sends a notification, via email, whenever a case is **updated**.
- Notify On Pending Internal Manual Input - It sends a notification, via email, whenever a manual input is created for an internal user with the option to send a customized email.
- Notify Failed Playbook Executions - It sends notification via email whenever a playbook's execution fails.

>[!NOTE]
>
>In-App Notifications have been disabled in SOAR Framework solution pack `v2.1.0` and later. If required then enable the **In-App Notifications** for desired rules.
>

## Pre-Processing Rules

Pre-processing rules provides a facility to make decisions based on predefined criteria before incoming records are created

The SOAR Framework includes the following pre-processing rule:

- Enforcing File Attachments for File Indicators - The rule ensures file indicators are only created when files are attached.

## Widgets

Widgets render information for the visual display inside View Template. Widget types vary such that specific widgets only correspond to certain view types. For example, the detail view has some exclusive widgets, such as Visual Correlation, Comments, Timeline, etc.

SOAR Framework has the following widgets:

| Widgets                            | Description                                                                                                                                                             |
|------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| AI Investigation Details           | AI Investigation Details widget to monitor AI Summary                                                                                                                   |
| AI Investigation Overview          | AI Investigation Overview of AI verdict, summary, key findings and highlighted feature                                                                                  |
| Card Table                         | This widget is used to show modules list, filter by group.                                                                                                              |
| Custom Picklist Message            | This widget helps display custom messages above the record details page.                                                                                                |
| Fields Of Interest                 | This widget helps users select fields to display in a module's detailed view, regardless of the *Visibility Constraint*.                                                |
| Incident Correlations              | This widget displays the correlation graph of a case.                                                                                                                   |
| Incident Timeline                  | This widget displays a vertical timeline showing a case record's correlated Alerts and Indicators, sorted based on user-selectable date fields.                         |
| Indicator Extraction Configuration | This widget assists user in configuring *Manage Indicator Exclusion List* settings within the FortiSOAR environment.                                                    |
| MITRE ATT&CK Alert Case Spread     | This widget displays detailed table view of Alerts and Cases linked to MITRE ATT&CK records.                                                                            |
| Picklist as Phases                 | This widget displays picklist values as phases in a flow diagram format. Each phase represents a specific state or stage in a process.                                  |
| Record Distribution                | This widget provides ability to visualize items/records and their correlations in different levels based on a given grouping context.                                   |
| Record Summary (War Room)          | It is primarily designed to showcase a particular record's highlights or summary, this widget houses multiple utility widgets within it to allow for customized uses.   |
| Setup Guide                        | The setup guide launches automatically on first login, for new installations, and contains a list of tasks whose completion is recommended as part of first time setup. |
| SLA Count Down Timer               | This widget displays the remaining time for an SLA.                                                                                                                     |
| System Overview                    | Real-time insights into resource utilization, service availability, and automation execution.                                                                           |
| Task Management (War Room)         | It is a comprehensive task management widget that helps users manage tasks and get visibility into the current task board.                                              |
| User Tile                          | This widget shows relevant information like alerts, cases, and tasks to users.                                                                                          |

## Dashboards

A Dashboard is the default landing page, and users' home page, that users see when they log into FortiSOAR. Dashboard, at a glance, shows them the critical tasks on which they need to work. SOAR Framework includes the following dashboards:

| Dashboards  | Description                                                                                                               |
|-------------|---------------------------------------------------------------------------------------------------------------------------|
| Analyst     | This dashboard displays alerts segregated by severity, type, priority, and criticality among other things.                |
| Overview    | This dashboard displays total alerts received, escalation ratio, time saved, and closure reasons among many other things. |
| ROI Summary | This dashboard displays total alerts resolved, last 30 days' escalation ratio, and ROI among many other things.           |
| SOC Admin   | This dashboard displays recent case, alerts, and assigned tasks                                                       |

## Reports

The reports module displays various reports for specific, defined users. SOAR framework includes the following reports:

| Reports                  |
|--------------------------|
| Case Summary Report      |
| High Impact Cases        |
| Overdue Alert Activities |
| Overdue Cases Activities |
| Unhandled Activities     |
| War Room Summary         |
| War Room Summary Reports |
| Weekly Alert Report      |
| Weekly Case Report       |
| Weekly IOC Report        |

## Reference Blocks

SOAR Framework includes following Reference Block(s)

| Block Name                                                                 | Description                                                                                                                                                                                                                        |
|----------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Approval-Based Decision                                                    | This reference block showcases an example of configuring a playbook to make a decision based on the approval provided.                                                                                                             |
| Bulk ingest records using the 'Ingest Bulk Feed' Step                      | This reference block showcases an example of configuring a playbook to insert high volumes of records using the 'Ingest Bulk Feed' step.                                                                                           |
| Calculate Severity using ResolveRange                                      | This reference block showcases an example of the use of resolveRange filter to get a specific value for a particular date range.                                                                                                   |
| Check if an IP address is Internal or External                             | This reference block showcases an example of configuring a playbook to check the IP address is in provided CIDR range.                                                                                                             |
| Condition-based Post-Create Trigger                                        | This reference block showcases an example of configuring a post-create triggered playbook and limiting its execution for a specific type of alert.                                                                                 |
| Condition-based Post-Create Trigger                                        | This reference block showcases an example of configuring a post-create triggered playbook and limiting its execution for a specific type of alert.                                                                                 |
| Condition-based Post-Update Trigger                                        | This reference block showcases an example of configuring post-update triggered playbooks and limiting their execution when a certain type of alert is updated.                                                                     |
| Create and Link Asset to Alert                                             | This reference block showcases an example of configuring a playbook that creates and links assets to the alert.                                                                                                                    |
| Execute Playbook Step using Do-Until Loop                                  | This reference block showcases an example of configuring a playbook to keep running a step until a specific condition is met using the 'do-until' loop from Step Utilities.                                                        |
| Execute Playbook Step using Parallel Looping                               | This reference block showcases an example of configuring a playbook to iterate the playbook step parallelly over the array of objects using the 'Loop' option from Step Utilities.                                                 |
| Execute Playbook step using Sequential Looping                             | This reference block showcases an example of configuring a playbook to iterate the playbook step sequentially over the array of objects using the 'Loop' option from Step Utilities.                                               |
| Execute Playbook using Mock Data                                           | This reference block showcases an example of configuring a playbook where you add sample data and execute a playbook step simulating the sample data as output.                                                                    |
| Extracting Artifacts from a String                                         | This reference block showcases an example of configuring a playbook to extract indicators from the given string using the Utilities connector                                                                                      |
| Fetch Emails From Particular Inbox in Exchange                             | This reference block showcases an example of configuring a playbook to fetch emails from a particular Inbox in Exchange.                                                                                                           |
| Handling Record Uniqueness (No Change Needed To Existing Record)           | This reference block showcases an example of configuring a 'Create Record Step' to keep playbook execution running and does not make any change to the existing record when a duplicate record is found.                           |
| Handling Record Uniqueness (Stop Process when Duplicate Record Found)      | This reference block showcases an example of configuring a 'Create Record Step' to stop the playbook execution when a duplicate record is found.                                                                                   |
| Handling Record Uniqueness (Update Existing Record - All Fields)           | This reference block showcases an example of configuring a 'Create Record Step' to keep the playbook execution going and updates the existing record with the new values when a duplicate record is found.                         |
| Handling Record Uniqueness (Update Existing Record - Only Selected Fields) | This reference block showcases an example of configuring a 'Create Record Step' to keep the playbook execution going and updates selected fields of the existing record with the new values only when a duplicate record is found. |
| Make a REST API Call                                                       | This reference block showcases an example of configuring a playbook to make a REST API call using the ""Utilities"" connector.                                                                                                     |
| Manual Trigger using User Input Prompt                                     | This reference block showcases an example of configuring a manually triggered playbook with a user prompt that asks the user to provide inputs before triggering the playbook.                                                     |
| Manual Trigger with Visibility Condition                                   | This reference block showcases an example of configuring a manually triggered playbook and limiting its visibility for only certain types of alerts.                                                                               |
| Manual Trigger without Selecting Records                                   | This reference block showcases an example of configuring manually triggered playbooks that run globally on an alert module without selecting an alert record and are used for ingesting data to create new alerts.                 |
| Posting a Message on Triggering Record (using Create Record Step)          | This reference block showcases an example of posting a message in the collaboration panel using the Create Record steps on the triggering record.                                                                                  |
| Posting a Message on Triggering Record (using Step Utilities)              | This reference block showcases an example of posting a message in the collaboration panel using the Step Utilities on the specified record.                                                                                        |
| Set New Variable to Store Record Information                               | This reference block showcases an example of declaring a new variable to store information received from the previous step.                                                                                                        |
| Using Code Snippet                                                         | This reference block showcases an example of the Code Snippet connector step in playbooks.                                                                                                                                         |
| Using Custom API Endpoint Trigger                                          | This reference block showcases an example of configuring an API-triggered playbook and capturing data sent by the API.                                                                                                             |
| Using Decision Step                                                        | This reference block showcases an example of the usage of Decision Step in a playbook and executing further playbooks based on the condition provided.                                                                             |
| Using Ignore Error to Avoid Playbook Failure                               | This reference block showcases an example of configuring a playbook step with an ""Ignore Error"" Option to avoid stopping playbooks execution due to step failure                                                                 |
| Using Manual Input Step                                                    | This reference block showcases an example of configuring a playbook with the Manual Input step                                                                                                                                     |
| Using Manual Task Step                                                     | This reference block showcases an example of configuring a playbook with the Manual Task step                                                                                                                                      |

## Playbook Collection

SOAR Framework includes the following playbook collections:

- 01 - Drafts
- 02 - Use Cases
- 03 - Enrich
- 03 - Triage
- 04 - Actions
- 05 - Hunt
- 06 - IRP - Case Management
- 06 - IRP - Communications Tracking
- 06 - IRP - Reporting
- 06 - IRP - War Room
- 07 - Case Response Plan
- 08 - Utilities

## Naming Convention

Playbooks follow a specific order of execution and are arranged in the same sequence as the flow of alert ingestion in the SOAR Framework. Hence the name carries a number that defines the order in which the playbooks run.

## Enrich Playbook Collection

Playbooks in the *03-Enrich* collection help perform enrichment of data &ndash; one of the first case response tasks. Automating data enrichment tasks helps better manage increasing volumes of threats and provides more actionable context to the analysts. An example of an enrichment type playbook would be retrieving the reputation of a file, domain, URL, etc. from threat intelligence platforms such as Anomali ThreatStream and VirusTotal.

| 03 - Enrich |
|-------------|


| Playbook Name                                           | Description                                                                                                                                              |
|---------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Asset - Get Running Process                             | Retrieves a list of all processes that are running on the specified host.                                                                                |
| Attachment - Get File Reputation                        | Retrieves the reputation of a file that is submitted from FortiSOAR to VirusTotal.                                                                       |
| Create Indicators (Batch)                               | Creates indicator records in bulk.                                                                                                                       |
| Enrich Indicator (Type IP)                              | Pre-process the IP Address indicator                                                                                                                     |
| Enrich Indicators (Type All)                            | Get indicator reputation from all available **pluggable** enrichment playbooks.                                                                          |
| Extract Indicators (Alerts)                             | Extracts and creates indicators from the specified data and then enriches specific fields in alerts with the indicator data.                             |
| Extract Indicators (Cases)                          | Extracts and creates indicators from the specified case records and then enriches specific fields in alerts with the indicator data.                 |
| Extract Indicators - Create File Indicator              | Creates File IOCs extracted from suspicious email attachments                                                                                            |
| Extract Indicators - Manual                             | Extracts and creates indicators from the specified alert records and then enriches specific fields in alerts with the indicator data.                    |
| Extract Indicators from Attachments                     | Extracts indicators from the attachment of the suspicious email                                                                                          |
| Get Related IOCs For An IP                              | Retrieves related IOCs for a specified IP address from threat intel sources.                                                                             |
| Get Reputation After Specified Time                     | Re-enriches indicators after a specified time.                                                                                                           |
| Get Unprocessed Indicators                              | Fetches the indicators for which enrichment has been failed and mark their `Enrichment Status` to Failed                                                 |
| Indicator (Manual Trigger) - Get Latest Reputation      | Retrieves the reputation of indicators using configured threat intelligence tools. You can trigger this playbook by manually selecting the indicator(s). |
| Indicator (Type Host) - Get Reputation                  | Retrieves the reputation of indicators of type 'Host' using configured threat intelligence tools.                                                        |
| Indicator (Type Port) - Get Reputation                  | Retrieves the reputation of indicators of type 'Port' using configured threat intelligence tools.                                                        |
| Indicator (Type Process) - Get Reputation               | Retrieves the reputation of indicators of type 'Process' using configured threat intelligence tools.                                                     |
| Indicator (Type Registry) - Get Reputation              | Retrieves the reputation of indicators of type 'Registry' using configured threat intelligence tools.                                                    |
| Reset Enrichment Global Variables                       | Reset the *pluggable* enrichment global variables                                                                                                        |
| Retrieve Configured Enrichment Connectors               | Retrieve the configured enrichment connectors and return their playbook IRI's                                                                            |
| Update/Initialize Indicator Enrichment Global Variables | Update enrichment playbooks list global variable based on indicator type defined as param tag                                                            |

## Triage Playbook Collection

Playbooks in the *03-Triage* collection perform actions such as sorting, systematizing, and computing your enriched data to help you quickly investigate the case and take decisions for containment and resolution of a case.

| 03 - Triage |
|-------------|


| Playbook Name                                                            | Description                                                                                                                                                                                                                                                       |
|--------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Compute Alert Priority Weight(Post Update)                               | Computes and sets the priority weight for an alert, when the alert is updated. The priority weight is calculated based on indicators related to the alert.                                                                                                        |
| Compute Alert Priority Weight(Post Update - Indicator Linked)            | Computes and sets the priority weight for an alert, when an indicator related to the alert is updated. The priority weight is calculated based on indicators related to the alert.                                                                                |
| Compute Alert Priority Weight(Post Update - Indicator Reputation Update) | Computes and sets the priority weight for an alert, when the reputation of an indicator is updated. The priority weight is calculated based on indicators related to the alert.                                                                                   |
| Find and Relate Similar Alerts                                           | Finds similar alerts based on the filter criteria you have specified and adds correlations to similar alerts.                                                                                                                                                     |
| Find and Relate Similar Alerts -ML                                       | Finds similar alerts based on the filter criteria you have specified and adds correlations to similar alerts using the recommendation APIs (ML).                                                                                                                  |
| Flag Indicators Linked Across Multiple Alerts                            | Flags changes made in indicators that are linked to multiple alerts.                                                                                                                                                                                              |
| Map Historical Alerts and escalate for malicious Indicators              | Creates a mapping for historical alerts and then escalates the alerts to cases if malicious indicators are found in the historical alerts. If the case already exists, then the information is updated into the case; else a new case is created. |
| Prioritize Alerts With VIP Assets                                        | Raises the severity of the alert if it is associated with a supercritical asset.                                                                                                                                                                                  |
| Update Alert Severity for malicious Indicators                           | Sets the severity of the alert to critical if its associated indicators are found to be 'malicious'.                                                                                                                                                              |

## Actions Playbook Collection

Playbooks in the *04-Actions* collection perform various operations such as blocking or unblocking domains, URLs, and hosts.

| 04 - Actions |
|--------------|


| Playbook Name                                         | Description                                                                                                                                                                                                                                 |
|-------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Action - Domain - Block(Indicator)                    | Blocks the indicators of type 'Domain' on the firewall and marks the indicator as "Blocked" based on its Block status.                                                                                                                      |
| Action - Domain - Block(Specified by User)            | Creates an indicator for the domain name specified by the user, blocks the domain on the firewall and also marks the status of the indicator 'Blocked'. The indicator is also linked to the record on which the playbook is triggered.      |
| Action - Domain - Unblock(Indicator)                  | Unblocks the indicators of type 'Domain' on the firewall and marks the indicator as "Unblocked" based on its block status.                                                                                                                  |
| Action - Domain - Unblock(Specified by User)          | Creates indicator for the domain name specified by the user, unblocks the domain on the firewall, and also marks the status of the indicator as 'Unblocked'. The indicator is also linked to the record on which the playbook is triggered. |
| Action - Email Address - Block(Indicator)             | Blocks the indicators of type 'Email Address' on the firewall and marks the indicator as "Blocked" based on its block status.                                                                                                               |
| Action - Email Address - Block(Specified by User)     | Creates indicator for the email address specified by the user, blocks the email on the firewall and marks the status of the indicator as 'Blocked'. The indicator is also linked to the record on which the playbook is triggered.          |
| Action - Email Address - Unblock(Indicator)           | Unblocks the indicators of type 'Email Address' on the firewall and marks the indicator as "Unblocked" based on its block status.                                                                                                           |
| Action - Email Address - Unblock(Specified by User)   | Creates indicators for the email address specified by the user, unblocks the email on the firewall, and also marks the status of the indicator as Unblocked. The indicator is also linked to the record on which the playbook is triggered. |
| Action - File - Block (Indicator)                     | Blocks the indicators of type 'File' on the firewall and marks the indicator as "Blocked" based on its block status.                                                                                                                        |
| Action - File - Block (Specified by user)             | Creates indicators for the file specified by the user, blocks the file on the firewall, and also marks the status of the indicator as blocked. The indicator is also linked to the record on which the playbook is triggered.               |
| Action - File - Unblock(Indicator)                    | Unblocks the indicators of type 'File' on the firewall and marks the indicator as "Unblocked" based on its block status.                                                                                                                    |
| Action - File - Unblock(Specified by User)            | Creates indicators for the file specified by the user, unblocks the file on the firewall, and also marks the status of the indicator as unblocked. The indicator is also linked to the record on which the playbook is triggered.           |
| Action - File MD5 - Block(Indicator)                  | Blocks the indicators of type 'Filehash' on the firewall and marks the indicator as "Blocked" based on its block status.                                                                                                                    |
| Action - File MD5 - Block(Specified by User)          | Creates indicators for the file hash specified by the user, blocks the indicator on the firewall, and also marks the status of the indicator as blocked. The indicator is also linked to the record on which the playbook is triggered.     |
| Action - File MD5 - Unblock(Specified by User)        | Creates indicators for the file hash specified by the user, unblocks the indicator on the firewall, and also marks the indicator as unblocked. The indicator is also linked to the record on which the playbook is triggered.               |
| Action - File MD5- Unblock(Indicator)                 | Unblocks the indicators of type 'Filehash' on the firewall and marks the indicator as "Unblocked" based on its block status.                                                                                                                |
| Action - Host - Block (Indicator)                     | Blocks indicators of type 'Host'on the firewall and marks the indicator as "Blocked" based on its block status.                                                                                                                             |
| Action - Host - Block (Specified by User)             | Creates indicators for the host specified by the user, blocks the host on the firewall, and also marks the indicator as blocked. The indicator is also linked to the record on which the playbook is triggered.                             |
| Action - Host - Isolate Host                          | Isolates indicators of type 'Host' and marks the indicator as "Isolated" based on its block status.                                                                                                                                         |
| Action - Host - Unblock(Indicator)                    | Unblocks indicators of type 'Host' on the firewall and marks the indicators as "Unblocked" based on their block status.                                                                                                                     |
| Action - Host - Unblock(Specified by User)            | Creates indicators for the host specified by the user, unblocks the host on the firewall, and also marks the indicator as Unblocked. The indicator is also linked to the record on which the playbook is triggered.                         |
| Action - IP Address - Block(FortiClient EMS)          | Quarantines endpoint with the specified IP address on FortiClient EMS.                                                                                                                                                                      |
| Action - IP Address - Block(FortiGate, FortiEDR)      | Isolates and blocks specified IP addresses using FortiGate and FortiEDR.                                                                                                                                                                    |
| Action - IP Address - Block(Indicator)                | Blocks indicators of type 'IPAddress' on the firewall and marks the indicators as "Blocked" based on their block status.                                                                                                                    |
| Action - IP Address - Block(Specified by User)        | Creates indicators for the specified IP Address', blocks the IP address on the firewall, and marks the indicators as blocked. The indicator is also linked to the record on which the playbook is triggered.                                |
| Action - IP Address - Unblock(Indicator)              | Unblocks indicators of type 'IPAddress' on the firewall and marks the indicator as "Unblocked" based on their block status.                                                                                                                 |
| Action - IP Address - Unblock(Specified by User)      | Creates indicators for the specified 'IP Address', unblocks the IP address on the firewall, and marks the indicators as unblocked. The indicator is also linked to the record on which the playbook is triggered.                           |
| Action - URL - Block (Indicator)                      | Blocks indicators of type 'URL'on the firewall and marks the indicators as "Blocked" based on their block status.                                                                                                                           |
| Action - URL - Block (Specified by User)              | Creates indicators for the specified 'URL', blocks the URL on the firewall, and marks the indicator as blocked. The indicator is also linked to the record on which the playbook is triggered.                                              |
| Action - URL - Unblock (Specified by User)            | Creates indicators for the specified 'URL', unblocks the URL on the firewall, and marks the indicator as unblocked. The indicator is also linked to the record on which the playbook is triggered.                                          |
| Action - URL - Unblock(Indicator)                     | Unblocks indicators of type 'URL'on the firewall and marks the indicators as "Unblocked" based on their block status.                                                                                                                       |
| Action -Asset Mitigation                              | Carries out a sequence of processes such as Clean Asset, AV scan, etc. to decide whether to keep an asset in isolation or remove it from isolation.                                                                                         |
| Action (Type All) - BlockIndicators                   | Blocks all types of indicators on the firewall based on their block status.                                                                                                                                                                 |
| Alert - Disable Specific User                         | Disables the specified UserAccount from the Active Directory.                                                                                                                                                                               |
| Asset - Deploy Patch                                  | Deploys the specified Patch on the selected asset using 'Microsoft SCCM'.                                                                                                                                                                   |
| Case - Get Running Process                        | Retrieves details for all the running processes on the specified host.                                                                                                                                                                      |
| Add Exclude List to Keystore                          | Add IP, Domain and URL in key store.                                                                                                                                                                                                        |
| Add Exclude List to Keystore - Update Keystore Record | Updates exclude list values in key store.                                                                                                                                                                                                   |

## Hunt Playbook Collection

Playbooks in the *05-Hunt* collection automate threat hunting processes, search, and identify suspicious domains, malware, and other indicators in your environment and create alerts based on them.

| 05 - Hunt |
|-----------|


| Playbook Name                                  | Description                                                                                                           |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------|
| Hunt Indicators                                | Searches for the specified indicators in your environment using EDR tools, and create alerts for ones that are found. |
| Hunt (On Create) - Initiate IOC Hunt           | This playbook initiates hunt on Hunt record and retrieve hunted data                                                  |
| Hunt Indicators (Type All)                     | Get indicator hunt result from all available pluggable hunt playbooks                                                 |
| Reset Hunt Global Variables                    | Reset the pluggable hunt global variables                                                                             |
| Indicator (Manual Trigger) - Initiate IOC Hunt | This Playbook executes hunt on indicator and retrieves hunted data                                                    |


## Case Management Collection

This playbook collection has the following playbook

- 06 - IRP - Case Management
- 06 - IRP - Communications Tracking
- 06 - IRP - Reporting
- 06 - IRP - War Room

| 06 - IRP - Case Management <a name="06-irp-case-management"></a> |
|------------------------------------------------------------------|


| Playbook Name                                    | Description                                                                                                                                                                                                       |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Alert - Close Corresponding SIEM Alert           | Closes the alert on the corresponding SIEM when an alert is closed in FortiSOAR.                                                                                                                                  |
| Alert - Escalate To Case                     | Escalates the selected alert to a case.                                                                                                                                                                      |
| Alert - Escalate to Case (Link Relations)    | Extracts related records and assigns them to a created case.                                                                                                                                                  |
| Alert - Escalate To Case (No Trigger)        | Creates a new case with the specified inputs and links the alert(s) to the newly created case.                                                                                                            |
| Alert - Escalate To Case (Referenced)        | Creates a new case with the given inputs and links the alert(s) to the newly created Case.                                                                                                                |
| Alert - Set Assigned Date (upon creation)        | Updates the assigned date of the alert when a person is assigned to the alert.                                                                                                                                    |
| Alert - Set Assigned Date (upon reassignment)    | Updates the assigned date of the alert when a person is reassigned to the alert.                                                                                                                                  |
| Alert - Set Resolved Date                        | Updates the resolved date of an alert when its state is marked as "Closed".                                                                                                                                       |
| Assign Random User to Unassigned Alerts          | Auto assigns alerts if their assignments were missed during alert creation.                                                                                                                                       |
| Assign Random User to Unassigned Cases       | Auto assigns cases if their assignments were missing during case creation.                                                                                                                                |
| Create IOC Extracted From CSV File               | It is subroutine of "Ingest IOC From CSV File" playbook, which will create IOC extracted from CSV File                                                                                                            |
| Case - Set Assigned Date (upon creation)     | Updates the assigned date of a case when a lead is assigned to the case.                                                                                                                                 |
| Case - Set Assigned Date (upon reassignment) | Updates the assigned date of the case when a lead is reassigned to the case.                                                                                                                              |
| Case - Set Phase Dates                       | Updates a case's phase dates based on case phase.                                                                                                                                                        |
| Case - Set Resolved Date                     | Updates the resolved date of a case when its state is marked as "Resolved".                                                                                                                                  |
| Case (Post Create) Phase Change              | Sets a case's phase dates upon case creation.                                                                                                                                                            |
| Case (Post Update) Phase Change              | Updates a case's phase dates when case phase is changed.                                                                                                                                                 |
| Indicator - Check Expiry Status                  | Checks periodically for the expiry date of the indicator and marks it as expired, if matched.                                                                                                                     |
| Indicator - Set Default Expiry Date              | Sets the default expiry date when an indicator is created.                                                                                                                                                        |
| Indicator - Set First Seen Date                  | Sets the first seen date when an indicator is created.                                                                                                                                                            |
| Indicator - Set Last Seen Date                   | Tracks the occurrence of an indicator by updating the last seen date.                                                                                                                                             |
| Ingest IOC From CSV File                         | Ingest and create indicators from IOC listed in CSV file. Incase CSV file has huge number of records , its recommended that celery soft timeout and tasks timeout values are updated. Refer product documentation |
| Link Similar Alerts                              | Links all selected similar alerts with the parent alert.                                                                                                                                                          |
| Link Similar Cases                           | Links all selected similar cases with the parent case.                                                                                                                                                    |
| Link Similar Indicators                          | Links all selected similar indicators with the parent indicator.                                                                                                                                                  |
| Notify Blocked Indicator Status to Linked Alerts | Adds a note about an indicator being blocked.                                                                                                                                                                     |
| Prompt when Indicator linked is to Campaign      | Notifies an analyst via manual input when an indicator is linked to a campaign.                                                                                                                                   |
| Resolve Alert                                    | Marks the specified Security Alert as closed.                                                                                                                                                                     |
| Set Prompt to an Alert                           | Displays a prompt on alerts when an indicator is linked to campaign.                                                                                                                                              |

| 06 - IRP - Communications Tracking |
|------------------------------------|


| Playbook Name                                | Description                                                                                                                                 |
|----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| Add Note for Communication Linked            | Adds a note stating a new communication has been linked to alert.                                                                           |
| Add Note for Communication Linked (Received) | Adds a note stating a new communication that was received has been linked to alert.                                                         |
| Create Communication Record                  | Creates a record in the communications module and links it to a respective module based on the information entered by the security analyst. |
| Create Communication Record (Alert)          | Creates a record in the communications module and links it to an alert based on the information provided by the security analyst.           |
| Create Communication Record (Email Reply)    | Creates a record in the communications module based off a reply to a received email.                                                        |
| Create Communication Record (Case)       | Creates a record in the communications module and links it to a case based on the information provided by the security analyst.        |
| Link Communication Record                    | Links the communication record to the corresponding alert based on the message ID.                                                          |
| Link Previous Communications                 | Links existing communications records to create a conversation thread.                                                                      |
| Manual Send Notification                     | Sends email notification for any selected communication record that is in either "Draft" or "Sending" state to the intended recipients.     |
| Send Notification                            | Sends auto-notification of any new communication record that is in the "Sending" state to the intended recipients.                          |

| 06 - IRP - Reporting |
|----------------------|


| Playbook Name         | Description                                                                                                             |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------|
| Export as CSV         | Export all records of the given module with specified filters in the CSV format.                                        |
| Get Paginated Records | Gets paginated records data and appends them in a .CSV file. This playbook is a reference playbook for 'Export as CSV'. |

| 06 - IRP - War Room |
|---------------------|


| Playbook Name                               | Description                                                                                                                                                     |
|---------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CascadeOwnership for Newly Linked Records   | Assigns war room responders as owners in all newly linked records such as alerts, cases, indicators, etc.                                                   |
| GenerateWar Room Report                     | Generates aWar Room Report and adds a link to the specific War Room record as a comment.                                                                        |
| Notify NewAnnouncement                      | Sends an email notification to the war room owner and user owners whenever a new announcement is created.                                                       |
| NotifyNewly Linked Team                     | Sends an email notification to the new team that has been linked to the War Room record.                                                                        |
| NotifyNewly Linked User(s)                  | Sends an email notification to the new users that have been linked to the War Room record.                                                                      |
| Send Email                                  | This child playbook of Send Email Notification. It sends an email notification to war room owners and user owners related to any changes in the War Room record. |
| Send EmailNotification                      | Fetches details of War Room owners and user owners and sends them an email notification related to any changes in the war room record.                          |
| Send WarRoom Summary Email                  | Generates and sends the War Room Summary report to the response team or specified user(s).                                                                      |
| Set up WarRoom from Alerts                  | Establishes a War Room based on the selected alert(s).                                                                                                          |
| Set up WarRoom from Cases               | Establishes a War Room based on the selected case(s).                                                                                                       |
| Set WarRoom Live and Notify Responders      | Updates the war room status to "Live" and sends the email notification to the responders.                                                                       |
| Update WarRoom Close Date                   | Updates the 'Close Date' of the War Room record, when its status is marked as "Closed".                                                                         |
| Set up War Room from Cases (Referenced) | Establishes a War Room based on the selected case(s)                                                                                                        |

## Case Response Playbook Collection

| 07 - Case Response Plan |
|-----------------------------|


| Playbook Name                                        | Description                                                                                                                |
|------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
| Case Response Plan (Type - Malware)              | Investigates cases of type 'Malware' and executes the different phases of case response using *VMware Carbon Black EDR*. |
| Case Response Plan (Type - NIST 800-61 -Generic) | Creates tasks for case response and handling as per the guidelines provided in NIST 800-61.                            |
| NIST 800-61 - Upfront Tasks                          | Creates tasks for case response and handling as per the guidelines provided in NIST 800-61.                            |

## Utilities Playbook

You can use the playbooks in the *08 - Utilities* collection to perform various operations in FortiSOAR such as creating and linking assets to specified emails, alerts, or cases, exporting all records or a specified module, or scheduling the health check of connectors and send appropriate notifications.

| 08 - Utilities |
|----------------|


| Playbook Name                                       | Description                                                                                                                                                        |
|-----------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Add Attacker Tag to Indicator (FortiDeceptor)       | Finds the Attacker IP Address in a FortiDeceptor alert and adds the Attacker Tag to the indicator as well as updates the reputation of the indicator to Malicious. |
| Alert - Record Closure Validation                   | Ensures alerts cannot be closed if tasks or manual inputs are incomplete, prompting user confirmation for reopening or closure.                                    |
| Cascade Permissions to all Related Records          | Cascades the team of the record to all of its related records. Earlier known as Fetch and Link Team to Related Records                                             |
| Create and Link Asset                               | Creates an asset (if it doesn't exist already), and links it to the specified email, alert, or case record.                                                    |
| Create and Link Indicator                           | Create an indicator (if it doesn't exist already), and link it to the specified email, alert, or case record.                                                  |
| Download and Create Attachment                      | Downloads the file from a specified URL and creates an attachment record for the same.                                                                             |
| Case - Record Closure Validation                | Ensures cases cannot be closed if tasks or manual inputs are incomplete, prompting user confirmation for reopening or closure.                                 |
| Indicator - Import Bulk Indicator                   | Extract Indicators from specified text                                                                                                                             |
| Manage Closed Alerts                                | Identifies closed alerts from the past seven days.                                                                                                                 |
| Manage Closed Alerts - Remove Pending Manual Inputs | Retrieves associated pending manual inputs and deletes them.                                                                                                       |
| Scheduled Configuration Export                      | Export template name and email address to be updated in the 'Configuration' step. Can be used to schedule Configuration Export and send it as an email.            |


# Next Steps

| [Installation](./setup.md#installation) | [Configuration](./setup.md#configuration) | [Usage](./usage.md) |
|-----------------------------------------|-------------------------------------------|---------------------|
