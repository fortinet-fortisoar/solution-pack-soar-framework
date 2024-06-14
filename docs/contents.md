| [Home](../README.md) |
|----------------------|

# Contents

This section lists the various contents of the SOAR Framework Solution Pack.

## Connector List

SOAR framework includes the following connectors:

| #  | Connector Names                         | Description                                                                                                                                                                                                                         |
|----|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | AlienVault-OTX                          | AlienVault-OTX is an open source repository of Indicators of Compromise (IOCs) supported by the community. This connector provides actions like Get IP Reputation, Create Pulse, and Get Domain Reputation.                         |
| 2  | APIVoid                                 | This connector provides several threat intelligence services ranging from IP/URL/Domain reputation to domain age and website screenshots                                                                                            |
| 3  | Exchange                                | This connector provides a robust, platform-independent, and simple interface for communicating with Microsoft Exchange 2007-2016 Server or Office 365 using Exchange Web Services (EWS).                                            |
| 4  | File Content Extraction                 | The connector uses is used to extract content, metadata and artifacts from over 1500 file types such as MS Office, PDF etc                                                                                                          |
| 5  | Fortinet FortiClient EMS                | This connector provides operations related to quarantine/unquarantine endpoints, get endpoint details, and is a security management solution that enables scalable and centralized management of multiple endpoints (computers).    |
| 6  | Fortinet FortiEDR                       | This connector facilitates the automated operations related to events, forensics and collectors.                                                                                                                                    |
| 7  | Fortinet FortiGate                      | Fortinet FortiGate enterprise firewall provide high performance, consolidated advanced security and granular visibility for broad protection across the entire digital attack surface.                                              |
| 8  | Fortinet FortiGuard Threat Intelligence | This connector facilitates automated operations to check IP, URL, Domain and File Hash Lookup’s and ingestion of daily threat feeds                                                                                                 |
| 9  | Fortinet FortiSandbox                   | FortiSandbox executes suspicious files in the VM host module to determine if the file is High, Medium, or Low Risk based on the behaviour observed in the VM sandbox module.                                                        |
| 10 | Fortinet FortiSIEM                      | FortiSIEM provides integrations that allow you to query and make changes to the CMDB, query events, and send incident notifications.                                                                                                |
| 11 | IBM XForce                              | This connector helps you rapidly research the latest global security threats, aggregate actionable intelligence, consult with experts, and collaborate with peers.                                                                  |
| 12 | IP Quality Score                        | The IP Quality Score (IPQS) Threat Intelligence application provides threat intelligence for IP addresses, email addresses, URLs, and domains via automated interactions with a IP Quality Score server using FortiSOAR™ playbooks. |
| 13 | IPStack                                 | IPStack provides geolocation facility for IP Address or Domain.                                                                                                                                                                     |
| 14 | MxToolbox                               | MxToolbox offers monitoring solutions and lookup tools. Connector supports automated operations for Lookup, Monitor and Usage                                                                                                       |
| 15 | NMAP Scanner                            | NMAP (Network Mapper) is a free and open-source security scanner used to discover hosts and services on a computer network, thus building a "map" of the network.                                                                   |
| 16 | SLA Calculator<sup style="color: red;">Migrated</sup>                           | Calculates SLA due date based on locale and work hours. This connector needs content pack for supporting playbooks and module changes                                                                                               |
| 17 | URLScan.io                              | URLScan.io provides a service that analyzes websites and the resources they request. URLScan.io provides actions like search domain, ip, hash scan URL and retrieve report of scanned url.                                          |
| 18 | VirusTotal                              | This connector facilitates automated operations such as scanning and analyzing suspicious files and URLs and retrieving reports from VirusTotal for files, IP addresses, and domains.                                               |
| 19 | VMWare Carbon Black EDR                 | This connector facilitates automated operation related to endpoint protection like isolate endpoint, unisolate endpoint, hunt file, terminate process etc. with VMWare Carbon Black EDR server.                                     |
| 20 | Whois RDAP                              | Whois RDAP is a service that enables you to retrieve information about the location of IP addresses, servers, or websites. You can find out the owner of the Internet resource and their contact details.                           |

## Modules

The SOAR framework includes the following modules:

| #  | Modules       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|----|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Alerts        | Alerts are primary actionable data elements that we obtain through a periodic ingestion process. We extract data through multiple channels like emails, SIEM platforms, or EDR platforms to create alerts. Once we have alerts, multiple playbooks are launched to extract and enrich the indicators.<br/><br/>To enhance or extend this default schema, refer to section [Extending Default Alert Schema](./extending-default-alert-schema.md).                                                                                                                               |
| 2  | Announcements | The announcements module helps notify users who are a part of a war room.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 3  | Assets        | Assets represent a unique piece of hardware and any information known about that hardware, such as MAC address, hostname, or IP address. Assets preferably have a unique identifier. The assets module helps add devices within FortiSOAR for use by the SOC team. Computers typically represent the assets of your organization.                                                                                                                                                                                                                                              |
| 4  | Campaigns     | Campaigns are a collection of incidents relatable to a single threat actor. Many times, disparate incidents are connected attempts of a malicious attacker attempting to probe and gain access to a network.                                                                                                                                                                                                                                                                                                                                                                   |
| 5  | Communication | It helps users to communicate with external entities like tenant contacts, and other SOC teams, using email, instant messaging (IM), etc. from within an alert generated in FortiSOAR. For this purpose, it uses IMAP and Exchange connectors.                                                                                                                                                                                                                                                                                                                                 |
| 6  | Events        | Events consist of records that contain machine-level information about activity that triggered a specific alert.                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| 7  | Hunt          | The Hunts module is a place to store and organize your hunts. The hunt you create here will be the central repository where all Alerts, Assets, Users, and other modules’ records that become associated with your hunting activity will be linked together.                                                                                                                                                                                                                                                                                                                   |
| 8  | Incidents     | Incidents are confirmed alerts that negatively affect the confidentiality, integrity, and availability of an organization. Incidents represent a collection of information discovered during an Incident Response investigation. Incidents are triggered based on the suspicion or confirmation of a security breach.                                                                                                                                                                                                                                                          |
| 9  | Indicators    | **Indicators of compromise** (IOCs) serve as evidence of probable intrusions on a host system or network. These artifacts help personnel at a Security Operations Center (SOC) to detect intrusion attempts or other malicious activities. IOCs help better analyze a particular malware’s techniques and behaviors and provide actionable threat intelligence to further improve an organization’s incident response strategies.<br/><br/>Some of this evidence of potential breach is found on event logs and timestamped entries in the system, applications, and services. |
| 10 | Key Store<sup style="color: red;">Migrated</sup>     | Key Store module is a place to store records that contains key-value pair                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 11 | SLA Template<sup style="color: red;">Migrated</sup>   | SLA Templates in FortiSOAR help create an in-built SLA management for incidents and alerts. For more information, please refer to [SLA Management](https://docs.fortinet.com/document/fortisoar/7.0.2/administration-guide/792686/sla-management).                                                                                                                                                                                                                                                                                                                             |
| 12 | War Rooms     | War Rooms in FortiSOAR is a collaborative space that enables SOC teams to mitigate a critical cyber threat scenario or campaign. FortiSOAR makes it easy for analysts to quickly and easily provision a War Room that allows participation of all stakeholders to analyze and collaborate to quickly mitigate the threat and restore the services. For more information, see the War Rooms chapter.                                                                                                                                                                            |

## Rules

Rules provide a framework to define a condition that generates notifications.

The SOAR Framework includes the following rules:

- Alert > Notify Creation - It sends a notification, via the email, whenever an alert is **created**.
- Alert > Notify Updates - It sends a notification, via the email, whenever an alert is **updated**.
- Incident > Notify Creation - It sends a notification, via the email, whenever an incident is **created**.
- Incident > Notify Updates - It sends a notification, via the email, whenever an incident is **updated**.
- Notify On Pending Internal Manual Input - It sends a notification, via the email, whenever a manual input is created for an internal user with the option to send a customized email.

<table>
    <tr>
        <th>NOTE</th>
        <td>In-App Notifications have been disabled in SOAR Framework solution pack <code>v2.1.0</code> and later. If required then enable the <strong>In-App Notifications</strong> for desired rules.</td>
    </tr>
</table>

## Widgets

Widgets render information for the visual display inside View Template. Widget types vary such that specific widgets only correspond to certain view types. For example, the detail view has some exclusive widgets, such as Visual Correlation, Comments, Timeline, etc.

SOAR Framework has the following widgets:

Here is the table sorted alphabetically by the "Widgets" column:

Here is the corrected table with the Serial Number column:

| #  | Widgets                                   | Description                                                                                                                                                           |
|----|-------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Custom Picklist Message                   | This widget helps display custom messages above the record details page.                                                                                              |
| 2  | Fields Of Interest                        | This widget helps users select fields to display in a module's detailed view, regardless of the *Visibility Constraint*.                                               |
| 3  | Incident Correlations                     | This widget displays the correlation graph of an incident.                                                                                                            |
| 4  | Incident Timeline                         | This widget displays a vertical timeline showing an Incident record's correlated Alerts and Indicators, sorted based on user-selectable date fields.                  |
| 5  | MITRE ATT&CK Alert Incident Spread        | This widget displays detailed table view of Alerts and Incidents linked to MITRE ATT&CK records.                                                                      |
| 6  | Picklist as Phases![](./res/icon-new.svg) | The widget displays picklist values as phases in a flow diagram format. Each phase represents a specific state or stage in a process.                                 |
| 7  | Record Distribution                       | This widget provides ability to visualize items/records and their correlations in different levels based on a given grouping context.                                 |
| 8  | Record Summary (War Room)                 | It is primarily designed to showcase a particular record's highlights or summary, this widget houses multiple utility widgets within it to allow for customized uses. |
| 9  | SLA Count Down Timer                      | This widget displays the remaining time for an SLA.                                                                                                                   |
| 10 | SOAR Framework Configuration Wizard![](./res/icon-new.svg)      | The wizard assists user in configuring SOAR settings within FortiSOAR environment. |
| 11 | Task Management (War Room)                | It is a comprehensive task management widget that helps users manage tasks and get visibility into the current task board.                                            |
| 12 | User Tile                                 | This widget shows relevant information like alerts, incidents, and tasks to users.                                                                                    |

## Roles

SOAR framework has the following roles included:

- SOC Analyst
- SOC Manager
- Full app permissions
- Read-Only User

## Dashboards

A Dashboard is the default landing page, and users' home page, that users see when they log into FortiSOAR. Dashboard, at a glance, shows them the critical tasks on which they need to work. SOAR Framework includes the following dashboards:

| # | Dashboards  | Description                                                                                                               |
|---|-------------|---------------------------------------------------------------------------------------------------------------------------|
| 1 | Analyst     | This dashboard displays alerts segregated by severity, type, priority, and criticality among other things.                |
| 2 | Overview    | This dashboard displays total alerts received, escalation ratio, time saved, and closure reasons among many other things. |
| 3 | ROI Summary | This dashboard displays total alerts resolved, last 30 days' escalation ratio, and ROI among many other things.           |
| 4 | SOC Admin   | This dashboard displays recent incident, alerts, and assigned tasks                                                       |

## Reports

The reports module displays various reports for specific, defined users. SOAR framework includes the following reports:

| #  | Reports                      |
|----|------------------------------|
| 1  | High Impact Incidents        |
| 2  | Incident Summary Report      |
| 3  | Overdue Alert Activities     |
| 4  | Overdue Incidents Activities |
| 5  | Unhandled Activities         |
| 6  | War Room Summary             |
| 7  | War Room Summary Reports     |
| 8  | Weekly Alert Report          |
| 9  | Weekly Incident Report       |
| 10 | Weekly IOC Report            |

## Reference Blocks

SOAR Framework includes following Reference Block(s)

| #  | Block Name                                                                 | Description                                                                                                                                                                                                                        |
|----|----------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Approval-Based Decision                                                    | This reference block showcases an example of configuring a playbook to make a decision based on the approval provided.                                                                                                             |
| 2  | Bulk ingest records using the 'Ingest Bulk Feed' Step                      | This reference block showcases an example of configuring a playbook to insert high volumes of records using the 'Ingest Bulk Feed' step.                                                                                           |
| 3  | Calculate Severity using ResolveRange                                      | This reference block showcases an example of the use of resolveRange filter to get a specific value for a particular date range.                                                                                                   |
| 4  | Check if an IP address is Internal or External                             | This reference block showcases an example of configuring a playbook to check the IP address is in provided CIDR range.                                                                                                             |
| 5  | Condition-based Post-Create Trigger                                        | This reference block showcases an example of configuring a post-create triggered playbook and limiting its execution for a specific type of alert.                                                                                 |
| 6  | Condition-based Post-Create Trigger                                        | This reference block showcases an example of configuring a post-create triggered playbook and limiting its execution for a specific type of alert.                                                                                 |
| 7  | Condition-based Post-Update Trigger                                        | This reference block showcases an example of configuring post-update triggered playbooks and limiting their execution when a certain type of alert is updated.                                                                     |
| 8  | Create and Link Asset to Alert                                             | This reference block showcases an example of configuring a playbook that creates and links assets to the alert.                                                                                                                    |
| 9  | Execute Playbook Step using Do-Until Loop                                  | This reference block showcases an example of configuring a playbook to keep running a step until a specific condition is met using the 'do-until' loop from Step Utilities.                                                        |
| 10 | Execute Playbook Step using Parallel Looping                               | This reference block showcases an example of configuring a playbook to iterate the playbook step parallelly over the array of objects using the 'Loop' option from Step Utilities.                                                 |
| 11 | Execute Playbook step using Sequential Looping                             | This reference block showcases an example of configuring a playbook to iterate the playbook step sequentially over the array of objects using the 'Loop' option from Step Utilities.                                               |
| 12 | Execute Playbook using Mock Data                                           | This reference block showcases an example of configuring a playbook where you add sample data and execute a playbook step simulating the sample data as output.                                                                    |
| 13 | Extracting Artifacts from a String                                         | This reference block showcases an example of configuring a playbook to extract indicators from the given string using the Utilities connector                                                                                      |
| 14 | Fetch Emails From Particular Inbox in Exchange                             | This reference block showcases an example of configuring a playbook to fetch emails from a particular Inbox in Exchange.                                                                                                           |
| 15 | Handling Record Uniqueness (No Change Needed To Existing Record)           | This reference block showcases an example of configuring a 'Create Record Step' to keep playbook execution running and does not make any change to the existing record when a duplicate record is found.                           |
| 16 | Handling Record Uniqueness (Stop Process when Duplicate Record Found)      | This reference block showcases an example of configuring a 'Create Record Step' to stop the playbook execution when a duplicate record is found.                                                                                   |
| 17 | Handling Record Uniqueness (Update Existing Record - All Fields)           | This reference block showcases an example of configuring a 'Create Record Step' to keep the playbook execution going and updates the existing record with the new values when a duplicate record is found.                         |
| 18 | Handling Record Uniqueness (Update Existing Record - Only Selected Fields) | This reference block showcases an example of configuring a 'Create Record Step' to keep the playbook execution going and updates selected fields of the existing record with the new values only when a duplicate record is found. |
| 19 | Make a REST API Call                                                       | This reference block showcases an example of configuring a playbook to make a REST API call using the ""Utilities"" connector.                                                                                                     |
| 20 | Manual Trigger using User Input Prompt                                     | This reference block showcases an example of configuring a manually triggered playbook with a user prompt that asks the user to provide inputs before triggering the playbook.                                                     |
| 21 | Manual Trigger with Visibility Condition                                   | This reference block showcases an example of configuring a manually triggered playbook and limiting its visibility for only certain types of alerts.                                                                               |
| 22 | Manual Trigger without Selecting Records                                   | This reference block showcases an example of configuring manually triggered playbooks that run globally on an alert module without selecting an alert record and are used for ingesting data to create new alerts.                 |
| 23 | Posting a Message on Triggering Record (using Create Record Step)          | This reference block showcases an example of posting a message in the collaboration panel using the Create Record steps on the triggering record.                                                                                  |
| 24 | Posting a Message on Triggering Record (using Step Utilities)              | This reference block showcases an example of posting a message in the collaboration panel using the Step Utilities on the specified record.                                                                                        |
| 25 | Set New Variable to Store Record Information                               | This reference block showcases an example of declaring a new variable to store information received from the previous step.                                                                                                        |
| 26 | Using Code Snippet                                                         | This reference block showcases an example of the Code Snippet connector step in playbooks.                                                                                                                                         |
| 27 | Using Custom API Endpoint Trigger                                          | This reference block showcases an example of configuring an API-triggered playbook and capturing data sent by the API.                                                                                                             |
| 28 | Using Decision Step                                                        | This reference block showcases an example of the usage of Decision Step in a playbook and executing further playbooks based on the condition provided.                                                                             |
| 29 | Using Ignore Error to Avoid Playbook Failure                               | This reference block showcases an example of configuring a playbook step with an ""Ignore Error"" Option to avoid stopping playbooks execution due to step failure                                                                 |
| 30 | Using Manual Input Step                                                    | This reference block showcases an example of configuring a playbook with the Manual Input step                                                                                                                                     |
| 31 | Using Manual Task Step                                                     | This reference block showcases an example of configuring a playbook with the Manual Task step                                                                                                                                      |

## Playbook Collection

SOAR Framework includes the following playbook collections:

- 01 – Drafts
- 02 - Use Cases
- 03 – Enrich
- 03 – Triage
- 04 – Actions
- 05 – Hunt
- 06 - IRP - Case Management
- 06 - IRP - Communications Tracking
- 06 - IRP – Reporting
- 06 - IRP - War Room
- 07 - Incident Response Plan
- 08 – Utilities

## Naming Convention

Playbooks follow a specific order of execution and are arranged in the same sequence as the flow of alert ingestion in the SOAR Framework. Hence the name carries a number that defines the order in which the playbooks run.

## Enrich Playbook Collection

Playbooks in the *03-Enrich* collection help perform enrichment of data &ndash; one of the first incident response tasks. Automating data enrichment tasks helps better manage increasing volumes of threats and provides more actionable context to the analysts. An example of an enrichment type playbook would be retrieving the reputation of a file, domain, URL, etc. from threat intelligence platforms such as Anomali ThreatStream and VirusTotal.

| 03 - Enrich |
|-------------|

| #  | Playbook Name                                              | Description                                                                                                                                              |
|----|------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Asset - Get Running Process                                | Retrieves a list of all processes that are running on the specified host.                                                                                |
| 2  | Attachment - Get File Reputation                           | Retrieves the reputation of a file that is submitted from FortiSOAR to VirusTotal.                                                                       |
| 3  | Create Indicators (Batch)                                  | Creates indicator records in bulk.                                                                                                                       |
| 4  | Enrich Indicator (Type IP)                                 | Pre-process the IP Address indicator                                                                                                                     |
| 5  | Enrich Indicators (Type All)                               | Get indicator reputation from all available **pluggable** enrichment playbooks.                                                                          |
| 6  | Extract Indicators (Alerts)<sup style="color: red;">Renamed</sup>                                | Extracts and creates indicators from the specified data and then enriches specific fields in alerts with the indicator data.                             |
| 7  | Extract Indicators (Incidents)<sup style="color: red;">New</sup>                | Extracts and creates indicators from the specified incident records and then enriches specific fields in alerts with the indicator data.                 |
| 8  | Extract Indicators - Create File Indicator  | Creates File IOCs extracted from suspicious email attachments                                                                                            |
| 9  | Extract Indicators - Manual                                | Extracts and creates indicators from the specified alert records and then enriches specific fields in alerts with the indicator data.                    |
| 10 | Extract Indicators from Attachments                        | Extracts indicators from the attachment of the suspicious email                                                                                          |
| 11 | Get Related IOCs For An IP                                 | Retrieves related IOCs for a specified IP address from threat intel sources.                                                                             |
| 12 | Get Reputation After Specified Time                        | Re-enriches indicators after a specified time.                                                                                                           |
| 13 | Get Unprocessed Indicators                                 | Fetches the indicators for which enrichment has been failed and mark their `Enrichment Status` to Failed                                                 |
| 14 | Indicator (Manual Trigger) - Get Latest Reputation         | Retrieves the reputation of indicators using configured threat intelligence tools. You can trigger this playbook by manually selecting the indicator(s). |
| 15 | Indicator (Type Host) - Get Reputation                     | Retrieves the reputation of indicators of type ‘Host’ using configured threat intelligence tools.                                                        |
| 16 | Indicator (Type Port) - Get Reputation                     | Retrieves the reputation of indicators of type ‘Port’ using configured threat intelligence tools.                                                        |
| 17 | Indicator (Type Process) - Get Reputation                  | Retrieves the reputation of indicators of type ‘Process’ using configured threat intelligence tools.                                                     |
| 18 | Indicator (Type Registry) - Get Reputation                 | Retrieves the reputation of indicators of type ‘Registry’ using configured threat intelligence tools.                                                    |
| 19 | Reset Enrichment Global Variables                          | Reset the *pluggable* enrichment global variables                                                                                                        |
| 20 | Retrieve Configured Enrichment Connectors                  | Retrieve the configured enrichment connectors and return their playbook IRI's                                                                            |
| 21 | Update/Initialize Indicator Enrichment Global Variables    | Update enrichment playbooks list global variable based on indicator type defined as param tag                                                            |

>**NOTE**: The playbooks marked *Deprecated* are to be deactivated if you are going for an upgrade.

## Triaging Playbook Collection

Playbooks in the *03-Triage* collection perform actions such as sorting, systematizing, and computing your enriched data to help you quickly investigate the incident and take decisions for containment and resolution of an incident.

| 03 - Triage |
|-------------|


| # | Playbook Name                                                            | Description                                                                                                                                                                                                                                                       |
|---|--------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1 | Compute Alert Priority Weight(Post Update)                               | Computes and sets the priority weight for an alert, when the alert is updated. The priority weight is calculated based on indicators related to the alert.                                                                                                        |
| 2 | Compute Alert Priority Weight(Post Update - Indicator Linked)            | Computes and sets the priority weight for an alert, when an indicator related to the alert is updated. The priority weight is calculated based on indicators related to the alert.                                                                                |
| 3 | Compute Alert Priority Weight(Post Update - Indicator Reputation Update) | Computes and sets the priority weight for an alert, when the reputation of an indicator is updated. The priority weight is calculated based on indicators related to the alert.                                                                                   |
| 4 | Find and Relate Similar Alerts                                           | Finds similar alerts based on the filter criteria you have specified and adds correlations to similar alerts.                                                                                                                                                     |
| 5 | Find and Relate Similar Alerts -ML                                       | Finds similar alerts based on the filter criteria you have specified and adds correlations to similar alerts using the recommendation APIs (ML).                                                                                                                  |
| 6 | Flag Indicators Linked Across Multiple Alerts                            | Flags changes made in indicators that are linked to multiple alerts.                                                                                                                                                                                              |
| 7 | Map Historical Alerts and escalate for malicious Indicators              | Creates a mapping for historical alerts and then escalates the alerts to incidents if malicious indicators are found in the historical alerts. If the incident already exists, then the information is updated into the incident; else a new incident is created. |
| 8 | Prioritize Alerts With VIP Assets                                        | Raises the severity of the alert if it is associated with a supercritical asset.                                                                                                                                                                                  |
| 9 | Update Alert Severity for malicious Indicators                           | Sets the severity of the alert to critical if its associated indicators are found to be ‘malicious’.                                                                                                                                                              |

## Actions Playbook Collection

Playbooks in the *04-Actions* collection perform various operations such as blocking or unblocking domains, URLs, and hosts.

| 04 - Actions |
|--------------|


| #  | Playbook Name                                       | Description                                                                                                                                                                                                                                 |
|----|-----------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Action - Domain - Block(Indicator)                  | Blocks the indicators of type'Domain' on the firewall and marks the indicator as "Blocked" based on its Block status.                                                                                                                       |
| 2  | Action - Domain - Block(Specified by User)          | Creates an indicator for the domain name specified by the user, blocks the domain on the firewall and also marks the status of the indicator 'Blocked’. The indicator is also linked to the record on which the playbook is triggered.      |
| 3  | Action - Domain - Unblock(Indicator)                | Unblocks the indicators of type'Domain' on the firewall and marks the indicator as "Unblocked" based on its block status.                                                                                                                   |
| 4  | Action - Domain - Unblock(Specified by User)        | Creates indicator for the domain name specified by the user, unblocks the domain on the firewall, and also marks the status of the indicator as ‘Unblocked’. The indicator is also linked to the record on which the playbook is triggered. |
| 5  | Action - Email Address - Block(Indicator)           | Blocks the indicators of type 'Email Address' on the firewall and marks the indicator as "Blocked" based on its block status.                                                                                                               |
| 6  | Action - Email Address - Block(Specified by User)   | Creates indicator for the email address specified by the user, blocks the email on the firewall and marks the status of the indicator as ‘Blocked’. The indicator is also linked to the record on which the playbook is triggered.          |
| 7  | Action - Email Address - Unblock(Indicator)         | Unblocks the indicators of type 'Email Address' on the firewall and marks the indicator as "Unblocked" based on its block status.                                                                                                           |
| 8  | Action - Email Address - Unblock(Specified by User) | Creates indicators for the email address specified by the user, unblocks the email on the firewall, and also marks the status of the indicator as Unblocked. The indicator is also linked to the record on which the playbook is triggered. |
| 9  | Action - File - Block (Indicator)                   | Blocks the indicators of type'File' on the firewall and marks the indicator as "Blocked" based on its block status.                                                                                                                         |
| 10 | Action - File - Block (Specified by user)           | Creates indicators for the file specified by the user, blocks the file on the firewall, and also marks the status of the indicator as blocked. The indicator is also linked to the record on which the playbook is triggered.               |
| 11 | Action - File - Unblock(Indicator)                  | Unblocks the indicators of type'File' on the firewall and marks the indicator as "Unblocked" based on its block status.                                                                                                                     |
| 12 | Action - File - Unblock(Specified by User)          | Creates indicators for the file specified by the user, unblocks the file on the firewall, and also marks the status of the indicator as unblocked. The indicator is also linked to the record on which the playbook is triggered.           |
| 13 | Action - File MD5 - Block(Indicator)                | Blocks the indicators of type'Filehash' on the firewall and marks the indicator as "Blocked" based on its block status.                                                                                                                     |
| 14 | Action - File MD5 - Block(Specified by User)        | Creates indicators for the file hash specified by the user, blocks the indicator on the firewall, and also marks the status of the indicator as blocked. The indicator is also linked to the record on which the playbook is triggered.     |
| 15 | Action - File MD5 - Unblock(Specified by User)      | Creates indicators for the file hash specified by the user, unblocks the indicator on the firewall, and also marks the indicator as unblocked. The indicator is also linked to the record on which the playbook is triggered.               |
| 16 | Action - File MD5- Unblock(Indicator)               | Unblocks the indicators of type'Filehash' on the firewall and marks the indicator as "Unblocked" based on its block status.                                                                                                                 |
| 17 | Action - Host - Block (Indicator)                   | Blocks indicators of type 'Host'on the firewall and marks the indicator as "Blocked" based on its block status.                                                                                                                             |
| 18 | Action - Host - Block (Specifiedby User)            | Creates indicators for the host specified by the user, blocks the host on the firewall, and also marks the indicator as blocked. The indicator is also linked to the record on which the playbook is triggered.                             |
| 19 | Action - Host - Isolate Host                        | Isolates indicators of type'Host' and marks the indicator as "Isolated" based on its block status.                                                                                                                                          |
| 20 | Action - Host - Unblock(Indicator)                  | Unblocks indicators of type'Host' on the firewall and marks the indicators as "Unblocked" based on their block status.                                                                                                                      |
| 21 | Action - Host - Unblock(Specified by User)          | Creates indicators for the host specified by the user, unblocks the host on the firewall, and also marks the indicator as Unblocked. The indicator is also linked to the record on which the playbook is triggered.                         |
| 22 | Action - IP Address - Block(Forticlient EMS)        | Quarantines endpoint with the specified IP address on FortiClient EMS.                                                                                                                                                                      |
| 23 | Action - IP Address - Block(Fortigate, FortiEDR)    | Isolates and blocks specified IP addresses using FortiGate and FortiEDR.                                                                                                                                                                    |
| 24 | Action - IP Address - Block(Indicator)              | Blocks indicators of type 'IPAddress' on the firewall and marks the indicators as "Blocked" based on their block status.                                                                                                                    |
| 25 | Action - IP Address - Block(Specified by User)      | Creates indicators for the specified IP Address', blocks the IP address on the firewall, and marks the indicators as blocked. The indicator is also linked to the record on which the playbook is triggered.                                |
| 26 | Action - IP Address - Unblock(Indicator)            | Unblocks indicators of type 'IPAddress' on the firewall and marks the indicator as "Unblocked" based on their block status.                                                                                                                 |
| 27 | Action - IP Address - Unblock(Specified by User)    | Creates indicators for the specified 'IP Address', unblocks the IP address on the firewall, and marks the indicators as unblocked. The indicator is also linked to the record on which the playbook is triggered.                           |
| 28 | Action - URL - Block (Indicator)                    | Blocks indicators of type 'URL'on the firewall and marks the indicators as "Blocked" based on their block status.                                                                                                                           |
| 29 | Action - URL - Block (Specifiedby User)             | Creates indicators for the specified 'URL', blocks the URL on the firewall, and marks the indicator as blocked. The indicator is also linked to the record on which the playbook is triggered.                                              |
| 30 | Action - URL - Unblock (Specifiedby User)           | Creates indicators for the specified 'URL', unblocks the URL on the firewall, and marks the indicator as unblocked. The indicator is also linked to the record on which the playbook is triggered.                                          |
| 31 | Action - URL - Unblock(Indicator)                   | Unblocks indicators of type 'URL'on the firewall and marks the indicators as "Unblocked" based on their block status.                                                                                                                       |
| 32 | Action -Asset Mitigation                            | Carries out a sequence of processes such as Clean Asset, AV scan, etc. to decide whether to keep an asset in isolation or remove it from isolation.                                                                                         |
| 33 | Action (Type All) - BlockIndicators                 | Blocks all types of indicators on the firewall based on their block status.                                                                                                                                                                 |
| 34 | Add to Exclude List                                 | Add IP, Domain and URL in Excluded Global Variables                                                                                                                                                                                         |
| 35 | Alert - Disable Specific User                       | Disables the specified UserAccount from the Active Directory.                                                                                                                                                                               |
| 36 | Asset - Deploy Patch                                | Deploys the specified Patch on the selected asset using 'Microsoft SCCM'.                                                                                                                                                                   |
| 37 | Incident - Get Running Process                      | Retrieves details for all the running processes on the specified host.                                                                                                                                                                      |

## Hunt Playbook Collection

Playbooks in the *05-Hunt* collection automate threat hunting processes, search, and identify suspicious domains, malware, and other indicators in your environment and create alerts based on them.

| 05 - Hunt |
|-----------|


| Playbook Name   | Description                                                                                                           |
|-----------------|-----------------------------------------------------------------------------------------------------------------------|
| Hunt Indicators | Searches for the specified indicators in your environment using EDR tools, and create alerts for ones that are found. |

## Case Management Collection

This playbook collection has the following playbook

- 06 - IRP - Case Management
- 06 - IRP - Communications Tracking
- 06 - IRP - Reporting
- 06 - IRP - War Room

| 06 - IRP - Case Management <a name="06-irp-case-management"></a> |
|------------------------------------------------------------------|


| #  | Playbook Name                                                           | Description                                                                                                                                                                                                       |
|----|-------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Alert - [01] Capture All SLA (Upon Create)<sup style="color: red;">Migrated</sup>                               | Updates the alert's acknowledgement due date and response due date based on the alert’s severity.                                                                                                                 |
| 2  | Alert - [02] Capture Ack SLA (Upon Update)<sup style="color: red;">Migrated</sup>                               | Updates the alert's acknowledgement date and SLA Status based on when the alert status is changed.                                                                                                                |
| 3  | Alert - [03] Capture Response SLA (Upon Update)<sup style="color: red;">Migrated</sup>                          | Updates the alert's response date and SLA Status based on when the alert status is changed.                                                                                                                       |
| 4  | Alert - [04] Check for SLA violations<sup style="color: red;">Migrated</sup>                                    | Checks periodically for violations of acknowledgement SLA of the open alerts.                                                                                                                                     |
| 5  | Alert - [05] Update Ack and Response Due dates (Post Severity Change)<sup style="color: red;">Migrated</sup>    | Updates the alert’s acknowledge due date and response due date for change in the severity of alerts                                                                                                               |
| 6  | Alert - Close Corresponding SIEM Alert                                  | Closes the alert on the corresponding SIEM when an alert is closed in FortiSOAR.                                                                                                                                  |
| 7  | Alert - Escalate To Incident                                            | Escalates the selected alert to an incident.                                                                                                                                                                      |
| 8  | Alert - Escalate to Incident (Link Relations)                           | Extracts related records and assigns them to a created incident.                                                                                                                                                  |
| 9  | Alert - Escalate To Incident (No Trigger)                               | Creates a new incident with the specified inputs and links the alert(s) to the newly created incident.                                                                                                            |
| 10 | Alert - Periodic Update Alert SLA Status<sup style="color: red;">Migrated</sup>                                 | This is a subroutine playbook to periodically check violations of acknowledgement and response SLA of the open alerts.                                                                                            |
| 11 | Alert - Set Assigned Date (upon creation)                               | Updates the assigned date of the alert when a person is assigned to the alert.                                                                                                                                    |
| 12 | Alert - Set Assigned Date (upon reassignment)                           | Updates the assigned date of the alert when a person is reassigned to the alert.                                                                                                                                  |
| 13 | Alert - Set Resolved Date                                               | Updates the resolved date of an alert when its state is marked as "Closed".                                                                                                                                       |
| 14 | Alert - Update SLA Details<sup style="color: red;">Migrated</sup>                                               | Updates an alert's acknowledgement due date and response due date based on the severity of the alert.                                                                                                             |
| 15 | Approval - On Create                                                    | This playbook is triggered whenever an approval record is created, and an email is sent out to the intended approver(s).                                                                                          |
| 16 | Approval - On Email Receipt - Process Email                             | Checks if the email is an approval email and returns its approval status.                                                                                                                                         |
| 17 | Approval - On Email Receipt (Exchange)                                  | This playbook is triggered whenever an email is received via Exchange; the playbook determines whether the received email is an approval mail, and, if yes, checks its approval status.                           |
| 18 | Approval - On Email Receipt (IMAP)                                      | This playbook is triggered whenever an email is received via IMAP and it checks whether the received email is an approval mail along with its approval status.                                                    |
| 19 | Assign Random User to Unassigned Alerts                                 | Auto assigns alerts if their assignments were missed during alert creation.                                                                                                                                       |
| 20 | Assign Random User to Unassigned Incidents                              | Auto assigns incidents if their assignments were missing during incident creation.                                                                                                                                |
| 21 | Create IOC Extracted From CSV File                                      | It is subroutine of “Ingest IOC From CSV File” playbook, which will create IOC extracted from CSV File                                                                                                            |
| 22 | Fetch SLA Details<sup style="color: red;">Migrated</sup>                                                        | Fetches SLA Details for incidents as per Service, that is, for MSSP or Enterprise.                                                                                                                                |
| 23 | Incident - [01] Capture All SLA (Upon Create)<sup style="color: red;">Migrated</sup>                            | Updates an alert's acknowledgement due date and response due date based on the severity of the incident.                                                                                                          |
| 24 | Incident - [02] Capture Ack SLA (Upon Update)<sup style="color: red;">Migrated</sup>                            | Updates an incident's acknowledgement date and SLA status when the status of the incident is changed.                                                                                                             |
| 25 | Incident - [03] Capture Response SLA (Upon Update)<sup style="color: red;">Migrated</sup>                       | Update an incident's response date and SLA status when the status of the incident is changed.                                                                                                                     |
| 26 | Incident - [04] Check for SLA violations<sup style="color: red;">Migrated</sup>                                 | Periodically check Acknowledgement SLA violations of the Open Incidents.                                                                                                                                          |
| 27 | Incident - [05] Update Response and Ack Due date (Post Severity Change)<sup style="color: red;">Migrated</sup>  | Update an incident's acknowledgement due date and response due date following a change in severity.                                                                                                               |
| 28 | Incident - [06] Check for Ack SLA violations<sup style="color: red;">Migrated</sup>                             | Notifies users of violation of Acknowledgement SLA.                                                                                                                                                               |
| 29 | Incident - [07] Check for Response SLA violations<sup style="color: red;">Migrated</sup>                        | Notifies users of violation of Response SLA.                                                                                                                                                                      |
| 30 | Incident - Periodic Update Incident SLA Status<sup style="color: red;">Migrated</sup>                           | This is a subroutine playbook to check and update an incident’s SLA status.                                                                                                                                       |
| 31 | Incident - Set Assigned Date (upon creation)                            | Updates the assigned date of an incident when a lead is assigned to the incident.                                                                                                                                 |
| 32 | Incident - Set Assigned Date (upon reassignment)                        | Updates the assigned date of the incident when a lead is reassigned to the incident.                                                                                                                              |
| 33 | Incident - Set Phase Dates                                              | Updates an incident's phase dates based on incident phase.                                                                                                                                                        |
| 34 | Incident - Set Resolved Date                                            | Updates the resolved date of an incident when its state is marked as "Resolved".                                                                                                                                  |
| 35 | Incident (Post Create) Phase Change                                     | Sets an incident's phase dates upon incident creation.                                                                                                                                                            |
| 36 | Incident (Post Update) Phase Change                                     | Updates an incident's phase dates when incident phase is changed.                                                                                                                                                 |
| 37 | Incidents - Update SLA Details<sup style="color: red;">Migrated</sup>                                           | Updates an alert's acknowledgement due date and response due date based on incident severity.                                                                                                                     |
| 38 | Indicator - Check Expiry Status                                         | Checks periodically for the expiry date of the indicator and marks it as expired, if matched.                                                                                                                     |
| 39 | Indicator - Set Default Expiry Date                                     | Sets the default expiry date when an indicator is created.                                                                                                                                                        |
| 40 | Indicator - Set First Seen Date                                         | Sets the first seen date when an indicator is created.                                                                                                                                                            |
| 41 | Indicator - Set Last Seen Date                                          | Tracks the occurrence of an indicator by updating the last seen date.                                                                                                                                             |
| 42 | Ingest IOC From CSV File                                                | Ingest and create indicators from IOC listed in CSV file. Incase CSV file has huge number of records , its recommended that celery soft timeout and tasks timeout values are updated. Refer product documentation |
| 43 | Link Similar Alerts                                                     | Links all selected similar alerts with the parent alert.                                                                                                                                                          |
| 44 | Link Similar Emails<sup>Deprecated</sup>                                | Links all selected similar emails with the parent email.                                                                                                                                                          |
| 45 | Link Similar Incidents                                                  | Links all selected similar incidents with the parent incident.                                                                                                                                                    |
| 46 | Link Similar Indicators                                                 | Links all selected similar indicators with the parent indicator.                                                                                                                                                  |
| 47 | Notify Ack SLA Violation<sup style="color: red;">Migrated</sup>                                                 | Checks every 5 minutes, for Acknowledgement SLA violations of open incidents.                                                                                                                                     |
| 48 | Notify Blocked Indicator Status to Linked Alerts                        | Adds a note about an indicator being blocked.                                                                                                                                                                     |
| 49 | Notify Response SLA Violation<sup style="color: red;">Migrated</sup>                                            | Checks every 5 minutes for Response SLA violations of acknowledged incidents.                                                                                                                                     |
| 50 | Pause SLA - Alerts<sup style="color: red;">Migrated</sup>                                                       | Pauses the alert's acknowledgement or response when its respective SLA status is changed to 'Awaiting Action'.                                                                                                    |
| 51 | Pause SLA - Incidents<sup style="color: red;">Migrated</sup>                                                    | Pauses the incident's acknowledgement or response SLA when its respective SLA status is changed to 'Awaiting Action'.                                                                                             |
| 52 | Prompt when Indicator linked is to Campaign                             | Notifies an analyst via manual input when an indicator is linked to a campaign.                                                                                                                                   |
| 53 | Resolve Alert                                                           | Marks the specified Security Alert as closed.                                                                                                                                                                     |
| 54 | Set Prompt to an Alert                                                  | Displays a prompt on alerts when an indicator is linked to campaign.                                                                                                                                              |

| 06 - IRP - Communications Tracking |
|------------------------------------|


| #  | Playbook Name                                | Description                                                                                                                                 |
|----|----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Add Note for Communication Linked            | Adds a note stating a new communication has been linked to alert.                                                                           |
| 2  | Add Note for Communication Linked (Received) | Adds a note stating a new communication that was received has been linked to alert.                                                         |
| 3  | Create Communication Record                  | Creates a record in the communications module and links it to a respective module based on the information entered by the security analyst. |
| 4  | Create Communication Record (Alert)          | Creates a record in the communications module and links it to an alert based on the information provided by the security analyst.           |
| 5  | Create Communication Record (Email Reply)    | Creates a record in the communications module based off a reply to a received email.                                                        |
| 6  | Create Communication Record (Incident)       | Creates a record in the communications module and links it to an incident based on the information provided by the security analyst.        |
| 7  | Link Communication Record                    | Links the communication record to the corresponding alert based on the message ID.                                                          |
| 8  | Link Previous Communications                 | Links existing communications records to create a conversation thread.                                                                      |
| 9  | Manual Send Notification                     | Sends email notification for any selected communication record that is in either “Draft” or “Sending” state to the intended recipients.     |
| 10 | Send Notification                            | Sends auto-notification of any new communication record that is in the “Sending” state to the intended recipients.                          |

| 06 - IRP - Reporting |
|----------------------|


| # | Playbook Name                          | Description                                                                                                             |
|---|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| 1 | Export as CSV                          | Export all records of the given module with specified filters in the CSV format.                                        |
| 2 | Export Selected Records<sup style="color: red;">Migrated</sup>                | Exports all selected records to a JSON file and creates an attachment record for the same.                              |
| 3 | Get Paginated Records                  | Gets paginated records data and appends them in a .CSV file. This playbook is a reference playbook for 'Export as CSV'. |
| 4 | Import Data<sup style="color: red;">Migrated</sup>                            | Imports a valid JSON file to a relevant module and creates subsequent records.                                          |
| 5 | Notify Connector Health Check Failures | Scheduled to check connectors’ health status and notify the specified recipients of any failed health check.            |
| 6 | Notify Failed Playbook Executions      | Notifies specified recipients of any playbook failure. It can be scheduled to run at specific intervals.                |

| 06 - IRP - War Room |
|---------------------|


| #  | Playbook Name                             | Description                                                                                                                                                     |
|----|-------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | CascadeOwnership for Newly Linked Records | Assigns war room responders as owners in all newly linked records such as alerts, incidents, indicators, etc.                                                   |
| 2  | GenerateWar Room Report                   | Generates aWar Room Report and adds a link to the specific War Room record as a comment.                                                                        |
| 3  | Notify NewAnnouncement                    | Sends an email notification to the war room owner and user owners whenever a new announcement is created.                                                       |
| 4  | NotifyNewly Linked Team                   | Sends an email notification to the new team that has been linked to the War Roomrecord.                                                                         |
| 5  | NotifyNewly Linked User(s)                | Sends an email notification to the new users that have been linked to the War Roomrecord.                                                                       |
| 6  | Send Email                                | This child playbook of Send Email Notification. It sends an email notification to war room owners and user owners related to any changes in the War Roomrecord. |
| 7  | Send EmailNotification                    | Fetchesdetails of War Room owners and user owners and sends them an email notification related to any changes in the war room record.                           |
| 8  | Send WarRoom Summary Email                | Generates and sends the War Room Summary report to the response team or specified user(s).                                                                      |
| 9  | Set up WarRoom from Alerts                | Establishes a War Room based on the selected alert(s).                                                                                                          |
| 10 | Set up WarRoom from Incidents             | Establishes a War Room based on the selected incident(s).                                                                                                       |
| 11 | Set WarRoom Live and Notify Responders    | Updates the war room status to "Live" and sends the email notification to the responders.                                                                       |
| 12 | Update WarRoom Close Date                 | Updates the ‘Close Date’ of the War Room record, when its status is marked as "Closed".                                                                         |

## Incident Response Playbook Collection

| 07 - Incident Response Plan |
|-----------------------------|


| # | Playbook Name                                        | Description                                                                                                                |
|---|------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
| 1 | Incident Response Plan (Type - Malware)              | Investigates incidents of type ‘Malware’ and executes the different phases of incident response using CarbonBlackResponse. |
| 2 | Incident Response Plan (Type - NIST 800-61 -Generic) | Creates tasks for incident response and handling as per the guidelines provided in NIST 800-61.                            |
| 3 | NIST 800-61 - Upfront Tasks                          | Creates tasks for incident response and handling as per the guidelines provided in NIST 800-61.                            |

## Utilities Playbook

You can use the playbooks in the *08 - Utilities* collection to perform various operations in FortiSOAR such as creating and linking assets to specified emails, alerts, or incidents, exporting all records or a specified module, or scheduling the health check of connectors and send appropriate notifications.

| 08 - Utilities |
|----------------|


| #  | Playbook Name                                                                      | Description                                                                                                                                                       |
|----|------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Activate Inactive Users<sup style="color: red;">Migrated</sup>                                                            | Find the Inactive users and activate them                                                                                                                         |
| 2  | Activate inactive users - Update user status<sup style="color: red;">Migrated</sup>                                       | This is a subroutine playbook to update the user status as active                                                                                                 |
| 3  | Add Attacker Tag to Indicator (FortiDeceptor)                                      | Finds the Attacker IP Address in a FortiDeceptoralert and adds the Attacker Tag to the indicator as well as updates the reputation of the indicator to Malicious. |
| 4  | Alert - Record Closure Validation                  | Ensures alerts cannot be closed if tasks or manual inputs are incomplete, prompting user confirmation for reopening or closure.                                   |
| 5  | Cascade Permissions to all Related Records                                         | Cascades the team of the record to all of its related records. Earlier known as Fetch and Link Team to Related Records                                            |
| 6  | Convert FortiSOAR User to SAML - Collect User Email IDs<sup style="color: red;">Migrated</sup>                            | Collects comma-separated Email-IDs of the existing FortiSOAR users that to be converted to SAML Users.                                                            |
| 7  | Convert FortiSOAR User to SAML - Update User Type<sup style="color: red;">Migrated</sup>                                  | Updates user type of existing FortiSOAR user to SAML.                                                                                                             |
| 8  | Create and Link Asset                                                              | Creates an asset (if it doesn't exist already), and links it to the specified email, alert, or incident record.                                                   |
| 9  | Create and Link Indicator                                                          | Create an indicator (if it doesn't exist already), and link it to the specified email, alert, or incident record.                                                 |
| 10 | Download and Create Attachment                                                     | Downloads the file from a specified URL and creates an attachment record for the same.                                                                            |
| 11 | Incident - Record Closure Validation                | Ensures incidents cannot be closed if tasks or manual inputs are incomplete, prompting user confirmation for reopening or closure.                                |
| 12 | Indicator - Import Bulk Indicator                                                  | Extract Indicators from specified text                                                                                                                            |
| 13 | Manage Closed Alerts                               | Identifies closed alerts from the past seven days.                                                                                                                |
| 14 | Manage Closed Alerts - Remove Pending Manual Inputs | Retrieves associated pending manual inputs and deletes them.                                                                                                      |
| 15 | Scheduled Configuration Export                                                     | Export template name and email address to be updated in the 'Configuration' step. Can be used to schedule Configuration Export and send it as an email.           |


| [Installation](./setup.md#installation) | [Configuration](./setup.md#configuration) | [Usage](./usage.md) |
|-----------------------------------------|-------------------------------------------|---------------------|
