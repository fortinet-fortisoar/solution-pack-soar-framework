| [Home](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/develop/README.md) |
|--------------------------------------------|

# Contents

This section lists the various contents of the SOAR Framework Solution Pack.

## Connector List

SOAR framework includes the following connectors:

| Sr. No. | Connector Names            | Description                                                                                                                                                                                                                      |
|---------|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1       | Active Directory           | Helps directly query AD to retrieve information about users, groups, and computers, in an organization, by using the Lightweight Directory Access Protocol (LDAP).                                                               |
| 2       | AlienVault-OTX             | AlienVault-OTX is an open source repository of Indicators of Compromise (IOCs) supported by the community. This connector provides actions like Get IP Reputation, Create Pulse, and Get Domain Reputation.                      |
| 3       | CarbonBlack Response       | This connector facilitates automated operation related to endpoint protection like isolate endpoint, unisolate endpoint, hunt file, terminate process etc. with CarbonBlack Response server.                                     |
| 4       | ElasticSearch              | ElasticSearch is a distributed, RESTful search, and analytics engine capable of solving a number of use cases. This connector facilitates automated operations to execute lucene query, get mapping and cluster details.         |
| 5       | Exchange                   | This connector provides a robust, platform-independent, and simple interface for communicating with Microsoft Exchange 2007-2016 Server or Office 365 using Exchange Web Services (EWS).                                         |
| 6       | Fortinet FortiClient EMS   | This connector provides operations related to quarantine/unquarantine endpoints, get endpoint details, and is a security management solution that enables scalable and centralized management of multiple endpoints (computers). |
| 7       | Fortinet FortiEDR          | This connector facilitates the automated operations related to events, forensics and collectors.                                                                                                                                 |
| 8       | Fortinet FortiGate         | Fortinet FortiGate enterprise firewall provide high performance, consolidated advanced security and granular visibility for broad protection across the entire digital attack surface.                                           |
| 9       | Fortinet FortiSandbox      | FortiSandbox executes suspicious files in the VM host module to determine if the file is High, Medium, or Low Risk based on the behaviour observed in the VM sandbox module.                                                     |
| 10      | Fortinet FortiSIEM         | FortiSIEM provides integrations that allow you to query and make changes to the CMDB, query events, and send incident notifications.                                                                                             |
| 11      | Fortinet Web Filter Lookup | Fortinet Web Filter Lookup allows users to check category and classification for any Domain                                                                                                                                      |
| 12      | IBM X-Force                | This connector helps you rapidly research the latest global security threats, aggregate actionable intelligence, consult with experts, and collaborate with peers.                                                               |
| 13      | IpStack                    | IPStack provides geolocation facility for IP Address or Domain.                                                                                                                                                                  |
| 14      | MxToolbox                  | MxToolbox offers monitoring solutions and lookup tools. Connector supports automated operations for Lookup, Monitor and Usage                                                                                                    |
| 15      | NMAP Scanner               | NMAP (Network Mapper) is a free and open-source security scanner used to discover hosts and services on a computer network, thus building a "map" of the network.                                                                |
| 16      | SLA Calculator             | Calculates SLA due date based on locale and work hours. This connector needs content pack for supporting playbooks and module changes                                                                                            |
| 17      | ThreatQ                    | ThreatQuotient (ThreatQ) delivers an open and extensible threat intelligence platform (TIP) to provide defenders the context, customization, and collaboration required to increase security effectiveness and efficiently handle threat operations and management.|
| 18      | URLScan.io                 | URLScan.io provides a service that analyzes websites and the resources they request. URLScan.io provides actions like search domain, ip, hash scan URL and retrieve report of scanned url.                                       |
| 19      | URLVoid                    | URLVoid provides a service to analyze websites through multiple blacklist engines and online reputation tools to facilitate the detection of fraudulent and malicious websites.                                                  |
| 20      | VirusTotal                 | This connector facilitates automated operations such as scanning and analyzing suspicious files and URLs and retrieving reports from VirusTotal for files, IP addresses, and domains.                                            |
| 21      | Whois RDAP                 | Whois RDAP is a service that enables you to retrieve information about the location of IP addresses, servers, or websites. You can find out the owner of the Internet resource and their contact details.|

## Modules

The SOAR framework includes the following modules:

| Sr. No. | Modules       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|---------|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1       | Alerts        | Alerts are primary actionable data elements that we obtain through a periodic ingestion process. We extract data through multiple channels like emails, SIEM platforms, or EDR platforms to create alerts. Once we have alerts, multiple playbooks are launched to extract and enrich the indicators.<br/><br/>To enhance or extend this default schema, refer to section [Extending Default Alert Schema](#extending-default-alert-schema).                                                                                                                                   |
| 2       | Announcements | The announcements module helps notify users who are a part of a war room.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 3       | Assets        | Assets represent a unique piece of hardware and any information known about that hardware, such as MAC address, hostname, or IP address. Assets preferably have a unique identifier. The assets module helps add devices within FortiSOAR for use by the SOC team. Computers typically represent the assets of your organization.                                                                                                                                                                                                                                              |
| 4       | Campaigns     | Campaigns are a collection of incidents relatable to a single threat actor. Many times, disparate incidents are connected attempts of a malicious attacker attempting to probe and gain access to a network.                                                                                                                                                                                                                                                                                                                                                                   |
| 5       | Communication | It helps users to communicate with external entities like tenant contacts, and other SOC teams, using email, instant messaging (IM), etc. from within an alert generated in FortiSOAR. For this purpose, it uses IMAP and Exchange connectors.                                                                                                                                                                                                                                                                                                                                 |
| 6       | Events        | Events consist of records that contain machine-level information about activity that triggered a specific alert.                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| 7       | Hunt          | The Hunts module is a place to store and organize your hunts. The hunt you create here will be the central repository where all Alerts, Assets, Users, and other modules’ records that become associated with your hunting activity will be linked together.                                                                                                                                                                                                                                                                                                                   |
| 8       | Incidents     | Incidents are confirmed alerts that negatively affect the confidentiality, integrity, and availability of an organization. Incidents represent a collection of information discovered during an Incident Response investigation. Incidents are triggered based on the suspicion or confirmation of a security breach.                                                                                                                                                                                                                                                          |
| 9       | Indicators    | **Indicators of compromise** (IOCs) serve as evidence of probable intrusions on a host system or network. These artifacts help personnel at a Security Operations Center (SOC) to detect intrusion attempts or other malicious activities. IOCs help better analyze a particular malware’s techniques and behaviors and provide actionable threat intelligence to further improve an organization’s incident response strategies.<br/><br/>Some of this evidence of potential breach is found on event logs and timestamped entries in the system, applications, and services. |
| 10      | SLA Template  | SLA Templates in FortiSOAR help create an in-built SLA management for incidents and alerts. For more information, please refer to [SLA Management](https://docs.fortinet.com/document/fortisoar/7.0.2/administration-guide/792686/sla-management).                                                                                                                                                                                                                                                                                                                             |
| 11      | War Rooms     | War Rooms in FortiSOAR is a collaborative space that enables SOC teams to mitigate a critical cyber threat scenario or campaign. FortiSOAR makes it easy for analysts to quickly and easily provision a War Room that allows participation of all stakeholders to analyze and collaborate to quickly mitigate the threat and restore the services. For more information, see the War Rooms chapter.                                                                                                                                                                            |

<!-- ## Alerts

Alerts are primary actionable data elements that we obtain through a periodic ingestion process. We extract data through multiple channels like emails, SIEM platforms, or EDR platforms to create alerts. Once we have alerts, multiple playbooks are launched to extract and enrich the indicators.

To enhance or extend this default schema, refer to section [Extending Default Alert Schema](#extending-default-alert-schema).

## Announcements

The announcements module helps notify users who are a part of a [war room](#war-rooms). 

## Assets

Assets represent a unique piece of hardware and any information known about that hardware, such as MAC address, hostname, or IP address. Assets preferably have a unique identifier. The assets module helps add devices within FortiSOAR for use by the SOC team. Computers typically represent the assets of your organization. 

## Campaigns

Campaigns are a collection of incidents relatable to a single threat actor. Many times, disparate incidents are connected attempts of a malicious attacker attempting to probe and gain access to a network.

## Communication

It helps users to communicate with external entities like tenant contacts, and other SOC teams, using email, instant messaging (IM), etc. from within an alert generated in FortiSOAR. For this purpose, it uses IMAP and Exchange connectors.

## Events

Events consist of records that contain machine-level information about activity that triggered a specific alert.

## Hunt

The Hunts module is a place to store and organize your hunts. The hunt you create here will be the central repository where all Alerts, Assets, Users, and other modules’ records that become associated with your hunting activity will be linked together. 

## Incidents

Incidents are confirmed alerts that negatively affect the confidentiality, integrity, and availability of an organization. Incidents represent a collection of information discovered during an Incident Response investigation. Incidents are triggered based on the suspicion or confirmation of a security breach.

## Indicators

**Indicators of compromise** (IOCs) serve as evidence of probable intrusions on a host system or network. These artifacts help personnel at a Security Operations Center (SOC) to detect intrusion attempts or other malicious activities. IOCs help better analyze a particular malware’s techniques and behaviors and provide actionable threat intelligence to further improve an organization’s incident response strategies.

Some of this evidence of potential breach is found on event logs and timestamped entries in the system, applications, and services.

## SLA Template

SLA Templates in FortiSOAR help create an in-built SLA management for incidents and alerts. For more information, please refer to [SLA Management](https://docs.fortinet.com/document/fortisoar/7.0.2/administration-guide/792686/sla-management). 

## War Rooms

War Rooms in FortiSOAR is a collaborative space that enables SOC teams to mitigate a critical cyber threat scenario or campaign. FortiSOAR makes it easy for analysts to quickly and easily provision a War Room that allows participation of all stakeholders to analyze and collaborate to quickly mitigate the threat and restore the services. For more information, see the War Rooms chapter. -->

## Naming Convention

Playbooks follow a specific order of execution and are arranged in the same sequence as the flow of alert ingestion in the SOAR Framework. Hence the name carries a number that defines the order in which the playbooks run.

## Rules

Rules provide a framework to define a condition that generates notifications.

The SOAR Framework includes the following rules:

- Alert > Notify Creation - It sends a notification, via the app or the email, whenever an alert is **created**.
- Alert > Notify Update - It sends a notification, via the app or the email, whenever an alert is **updated**.
- Incident > Notify Creation - It sends a notification, via the app or the email, whenever an incident is **created**.
- Incident > Notify Update - It sends a notification, via the app or the email, whenever an incident is **updated**.

## Widgets

Widgets render information for the visual display inside View Template. Widget types vary such that specific widgets only correspond to certain view types. For example, the detail view has some exclusive widgets, such as Visual Correlation, Comments, Timeline, etc.

SOAR Framework has the following widgets:

| Widgets                    | Description                                                                                                                                                           |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Task Management (War Room) | It is a comprehensive task management widget that helps users manage tasks and get visibility into the current task board.                                            |
| Record Summary (War Room)  | It is primarily designed to showcase a particular record's highlights or summary, this widget houses multiple utility widgets within it to allow for customized uses. |
| SLA Count Down Timer       | This widget displays the remaining time for an SLA.                                                                                                                   |
| User Tile                  | This widget shows relevant information like alerts, incidents, and tasks to users.                                                                                    |
| Incident Correlations      | This widget displays the correlation graph of an incident.                                                                                                            |
| Access Control             | This widget helps you manage the teams/users who have access to records.                                                                                              |
| Custom Picklist Message    | This widget helps display custom messages above the record details page.                                                                                              |
| Incident Timeline          | This widget displays a vertical timeline showing an Incident record's correlated Alerts and Indicators, sorted based on user-selectable date fields.                  |


## Roles

SOAR framework has the following roles included:

- SOC Analyst
- SOC Manager
- Full app permissions

## Dashboards

A Dashboard is the default landing page, and users' home page, that users see when they log into FortiSOAR. Dashboard, at a glance, shows them the critical tasks on which they need to work. SOAR Framework includes the following dashboards:

| Sr. No. | Dashboards  | Description                                                                                                     |
|---------|-------------|-----------------------------------------------------------------------------------------------------------------|
| 1       | Overview    | This dashboard displays total alerts received, escalation ratio, and time saved among many other things.        |
| 2       | ROI Summary | This dashboard displays total alerts resolved, last 30 days' escalation ratio, and ROI among many other things. |
| 3       | SOC Admin   | This dashboard displays recent incident, alerts, and assigned tasks                                             |
| 4       | Analyst     | This dashboard displays alerts segregated by severity, type, priority, and criticality among other things.      |

## Reports

The reports module displays various reports for specific, defined users. SOAR framework includes the following reports:

| Sr. No. | Reports                      |
|---------|------------------------------|
| 1       | High Impact Incidents        |
| 2       | Incident Summary Report      |
| 3       | Overdue Alert Activities     |
| 4       | Overdue Incidents Activities |
| 5       | Unhandled Activities         |
| 6       | War Room Summary Reports     |
| 7       | War Room Summary             |
| 8       | Weekly Alert Report          |
| 9       | Weekly IOC Report            |
| 10      | Weekly Incident Report       |

## Playbook Collection

SOAR Framework includes the following playbook collections:

- 01 – Drafts
- 02 - Use Cases
- 03 – Enrich (22)
- 03 - Enrich (Pluggable) (36)
- 03 – Triage
- 04 – Actions (36)
- 05 – Hunt
- 06 - IRP - Case Management (54)
- 06 - IRP - Communications Tracking
- 06 - IRP – Reporting
- 06 - IRP - War Room (12)
- 07 - Incident Response Plan
- 08 – Utilities

## Enrich Playbook Collection

It has two playbook collections

- 03 - Enrich
- 03 - Enrich (Pluggable)

### 03 - Enrich

Playbooks in the *03-Enrich* collection help perform enrichment of data -- one of the first incident response tasks. Automating data enrichment tasks helps better manage increasing volumes of threats and provides more actionable context to the analysts. An example of an enrichment type playbook would be retrieving the reputation of a file, domain, URL, etc. from threat intelligence platforms such as Anomali ThreatStream and VirusTotal.

Following is a table that lists the playbooks that are part of the *“03-Enrich”*collection in the Solution Pack:

| Sr. No | Name of the playbook                                     | Description                                                                                                                                              |
|--------|----------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1      | Asset - Get Running Process                              | Retrieves a list of all processes that are running on the specified host.                                                                                |
| 2      | Attachment - Get File Reputation                         | Retrieves the reputation of a file that is submitted from FortiSOAR to VirusTotal.                                                                       |
| 3      | Create Indicators (Batch)                                | Creates indicator records in bulk.                                                                                                                       |
| 4      | Extract Indicators                                       | Extracts and creates indicators from the specified data and then enriches specific fields in alerts with the indicator data.                             |
| 5      | Extract Indicators - Manual                              | Extracts and creates indicators from the specified alert records and then enriches specific fields in alerts with the indicator data.                    |
| 6      | Fotinet Fortisandbox (GetReputation) - Get Scan Results  | Retrieves the job verdict details for submitted samples based on the specified job ID.                                                                   |
| 7      | Get Related IOCs For An IP                               | Retrieves related IOCs for a specified IP address from threat intel sources.                                                                             |
| 8      | Get Reputation After SpecifiedTime                       | Re-enriches indicators after a specified time.                                                                                                           |
| 9      | Indicator (Manual Trigger)-Get Latest Reputation         | Retrieves the reputation of indicators using configured threat intelligence tools. You can trigger this playbook by manually selecting the indicator(s). |
| 10     | Indicator (Type All) - Get LatestReputation              | Based on the type of indicator, this playbook retrieves the reputation of indicators using configured threat intelligence tools.                         |
| 11     | Indicator (Type Domain) - GetReputation                  | Retrieves the reputation of indicators of type ‘Domain’ using configured threat intelligence tools.                                                      |
| 12     | Indicator (Type Email) - GetReputation                   | Retrieves the reputation of indicators of type ‘Email Address’ using configured threat intelligence tools.                                               |
| 13     | Indicator (Type File) - GetReputation                    | Uploads a file to a sandbox and then retrieves its reputation using configured threat intelligence tools.                                                |
| 14     | Indicator (Type File) - GetReputation (Fortinet Sandbox) | Submits a file to FortinetSandbox and then retrieves its reputation.                                                                                     |
| 15     | Indicator (Type File - MD5) - GetReputation              | Retrieves the reputation of a file, identified by its MD5 hash, using configured threat intelligence tools.                                              |
| 16     | Indicator (Type Host) - GetReputation                    | Retrieves the reputation of indicators of type ‘Host’ using configured threat intelligence tools.                                                        |
| 17     | Indicator (Type IP) - GetReputation                      | Retrieves the reputation of indicators of type ‘IP Address’ using configured threat intelligence tools.                                                  |
| 18     | Indicator (Type Port) - GetReputation                    | Retrieves the reputation of indicators of type ‘Port’ using configured threat intelligence tools.                                                        |
| 19     | Indicator (Type Process) - GetReputation                 | Retrieves the reputation of indicators of type ‘Process’ using configured threat intelligence tools.                                                     |
| 20     | Indicator (Type URL) - GetReputation                     | Retrieves the reputation of indicators of type ‘URL’ using configured threat intelligence tools.                                                         |
| 21     | Indicator (Type URL) - GetReputation (Fortinet Sandbox)  | Submit URL to FortinetFortiSandbox.                                                                                                                      |
| 22     | Indicator (Type User Account) -Get Details               | Retrieves the details of indicators of type ‘User Account’ using configured threat intelligence tools.                                                   |

### 03 - Enrich (Pluggable)

The function of the playbooks in both *Enrich* and *Enrich (Pluggable)* collections is the same; however, the design approach is different. In the standard *Enrich* playbook, all threat intelligence platforms for a particular indicator type are configured in a single playbook. In *Enrich (Pluggable)* collection, every threat intelligence platform for a particular indicator type has a separate playbook, which can be plugged in or referenced to the enrichment playbook.

| Sr. No. | Name of the playbook                                 | Description                                                                                                                                              |
|---------|------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1       | AlienValut OTX - File MD5Reputation                  | Retrieves the reputation of indicators of type 'FileHash-MD5' using AlienValut OTX.                                                                      |
| 2       | AlienValut OTX - IP Reputation                       | Retrieves the reputation of indicators of type 'IP Address' using AlienValut OTX.                                                                        |
| 3       | AlienValut OTX - URL Reputation                      | Retrieves the reputation of indicators of type 'URL' using AlienValut OTX.                                                                               |
| 4       | AlienVault-OTX - DomainReputation                    | Retrieves the reputation of indicators of type 'Domain' using AlienValut OTX.                                                                            |
| 5       | Anomali Threatstream - DomainReputation              | Retrieves the reputation of indicators of type 'Domain' using Anomali Threatstream.                                                                      |
| 6       | Anomali Threatstream - EmailReputation               | Retrieves the reputation of indicators of type 'Email' using Anomali Threatstream.                                                                       |
| 7       | Anomali Threatstream - File MD5Reputation            | Retrieves the reputation of indicators of type 'FileHash-MD5' using Anomali Threatstream.                                                                |
| 8       | Anomali Threatstream - IPReputation                  | Retrieves the reputation of indicators of type 'IP Address' using Anomali Threatstream.                                                                  |
| 9       | Anomali Threatstream - URLReputation                 | Retrieves the reputation of indicators of type 'URL' using Anomali Threatstream.                                                                         |
| 10      | Cisco Threat Grid - FileReputation                   | Submits a file to Cisco ThreatGrid and then retrieves its reputation.                                                                                    |
| 11      | Fortinet Web Filter Lookup -Domain Reputation        | Retrieves the reputation of indicators of type 'Domain' using Fortinet Web Filter Lookup.                                                                |
| 12      | Fortinet Web Filter Lookup - URLReputation           | Retrieves the reputation of indicators of type 'URL' using Fortinet Web Filter Lookup.                                                                   |
| 13      | IP Stack - Domain Geo Location                       | Retrieves the geolocation of indicators of type 'Domain' using IP Stack.                                                                                 |
| 14      | IP Stack - IP Reputation                             | Retrieves the geolocation of indicators of type 'IP Address' using IP Stack.                                                                             |
| 15      | Indicator (Domain) - Get LatestReputation            | Retrieves the reputation of indicators of type 'Domain' using configured threat intelligence playbooks.                                                  |
| 16      | Indicator (Email) - Get LatestReputation             | Retrieves the reputation of indicators of type 'Email' using configured threat intelligence playbooks.                                                   |
| 17      | Indicator (File MD5) - Get LatestReputation          | Retrieves the reputation of indicators of type 'Filehash' using configured threat intelligence playbooks.                                                |
| 18      | Indicator (File) - Get LatestReputation              | Uploads a file to a sandbox and then retrieves its reputation using configured threat intelligence tools playbooks.                                      |
| 19      | Indicator (IP Address) - GetLatest Reputation        | Retrieves the reputation of indicators of type 'IP Address' using configured threat intelligence playbooks.                                              |
| 20      | Indicator (Manual Trigger)- Get Latest Reputation    | Retrieves the reputation of indicators using configured threat intelligence tools. You can trigger this playbook by manually selecting the indicator(s). |
| 21      | Indicator (Type All) - Get LatestReputation          | Based on the type of indicator, this playbook retrieves the reputation of indicators using configured threat intelligence tools.                         |
| 22      | Indicator (Type File - MD5) - GetReputation          | Retrieves the reputation of a file, identified by its MD5 hash, using configured threat intelligence tools.                                              |
| 23      | Indicator (Type Host) - GetLatest Reputation         | Retrieves the reputation of indicators of type 'Host' using configured threat intelligence playbooks.                                                    |
| 24      | Indicator (Type Process) - GetLatest Reputation      | Retrieves the reputation of indicators of type 'Process' using configured threat intelligence tools.                                                     |
| 25      | Indicator (URL) - Get the latest reputation          | Retrieves the reputation of indicators of type 'URL' using configured threat intelligence playbooks.                                                     |
| 26      | MXToolBox - IP Reputation                            | Retrieves the reputation of indicators of type 'IP Address' using MXToolBox.                                                                             |
| 27      | Symantec Deepsight Intelligence -File MD5 Reputation | Retrieves the reputation of a file, identified by its MD5 hash, using Symantec DeepSight Intelligence.                                                   |
| 28      | ThreatQ - Email Reputation                           | Retrieves the reputation of indicators of type 'Email' using ThreatQ.                                                                                    |
| 29      | URLVoid - Domain Reputation                          | Retrieves the reputation of indicators of type 'Domain' using URLVoid.                                                                                   |
| 30      | URLVoid - URL Reputation                             | Retrieves the reputation of indicators of type 'URL' using URLVoid.                                                                                      |
| 31      | VirusTotal - Domain Reputation                       | Retrieves the reputation of indicators of type 'Domain' using VirusTotal.                                                                                |
| 32      | VirusTotal - URL Reputation                          | Retrieves the reputation of indicators of type 'URL' using VirusTotal.                                                                                   |
| 33      | Virustotal - File MD5 Reputation                     | Retrieves the reputation of indicators of type 'File Hash MD5' using VirusTotal.                                                                         |
| 34      | Virustotal - File Reputation                         | Submits a file to VirusTotal and then retrieves its reputation.                                                                                          |
| 35      | Virustotal - IP Reputation                           | Retrieves the reputation of indicators of type 'IP Address' using VirusTotal.                                                                            |
| 36      | Whois - IP Reputation                                | Retrieves whois data for indicators of type 'IP Address' using Whois RDAP.                                                                               |

## Triaging Playbook Collection

This playbook collection appears with the name 

- 03 - Triage

### 03 - Triage

Playbooks in the *03-Triage* collection perform actions such as sorting, systematizing, and computing your enriched data to help you quickly investigate the incident and take decisions for containment and resolution of an incident.

Following is a table that lists the playbooks that are part of the *“03-Triage”*collection in the Solution Pack:

| Sr. No | Name of the playbook                                                     | Description                                                                                                                                                                                                                                                       |
|--------|--------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1      | Compute Alert Priority Weight(Post Update)                               | Computes and sets the priority weight for an alert, when the alert is updated. The priority weight is calculated based on indicators related to the alert.                                                                                                        |
| 2      | Compute Alert Priority Weight(Post Update - Indicator Linked)            | Computes and sets the priority weight for an alert, when an indicator related to the alert is updated. The priority weight is calculated based on indicators related to the alert.                                                                                |
| 3      | Compute Alert Priority Weight(Post Update - Indicator Reputation Update) | Computes and sets the priority weight for an alert, when the reputation of an indicator is updated. The priority weight is calculated based on indicators related to the alert.                                                                                   |
| 4      | Find and Relate Similar Alerts                                           | Finds similar alerts based on the filter criteria you have specified and adds correlations to similar alerts.                                                                                                                                                     |
| 5      | Find and Relate Similar Alerts -ML                                       | Finds similar alerts based on the filter criteria you have specified and adds correlations to similar alerts using the recommendation APIs (ML).                                                                                                                  |
| 6      | Flag Indicators Linked across multiple alerts                            | Flags changes made in indicators that are linked to multiple alerts.                                                                                                                                                                                              |
| 7      | Map Historical Alerts and escalate for malicious Indicators              | Creates a mapping for historical alerts and then escalates the alerts to incidents if malicious indicators are found in the historical alerts. If the incident already exists, then the information is updated into the incident; else a new incident is created. |
| 8      | Prioritize Alerts With VIP Assets                                        | Raises the severity of the alert if it is associated with a supercritical asset.                                                                                                                                                                                  |
| 9      | Update Alert Severity for malicious Indicators                           | Sets the severity of the alert to critical if its associated indicators are found to be ‘malicious’.                                                                                                                                                              |

## Actions Playbook Collection

Playbooks in the *04-Actions* collection perform various operations such as blocking or unblocking domains, URLs, and hosts.

### 04 - Actions

Following is a table that lists the playbooks that are a part of the *04-Actions* collection in the Solution Pack:

| Sr. No. | Name of the playbook                                | Description                                                                                                                                                                                                                                 |
|---------|-----------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1       | Action -Asset Mitigation                            | Carries out a sequence of processes such as Clean Asset, AV scan, etc. to decide whether to keep an asset in isolation or remove it from isolation.                                                                                         |
| 2       | Action - Domain - Block(Indicator)                  | Blocks the indicators of type'Domain' on the firewall and marks the indicator as "Blocked" based on its Block status.                                                                                                                       |
| 3       | Action - Domain - Block(Specified by User)          | Creates an indicator for the domain name specified by the user, blocks the domain on the firewall and also marks the status of the indicator 'Blocked’. The indicator is also linked to the record on which the playbook is triggered.      |
| 4       | Action - Domain - Unblock(Indicator)                | Unblocks the indicators of type'Domain' on the firewall and marks the indicator as "Unblocked" based on its block status.                                                                                                                   |
| 5       | Action - Domain - Unblock(Specified by User)        | Creates indicator for the domain name specified by the user, unblocks the domain on the firewall, and also marks the status of the indicator as ‘Unblocked’. The indicator is also linked to the record on which the playbook is triggered. |
| 6       | Action - Email Address - Block(Indicator)           | Blocks the indicators of type 'Email Address' on the firewall and marks the indicator as "Blocked" based on its block status.                                                                                                               |
| 7       | Action - Email Address - Block(Specified by User)   | Creates indicator for the email address specified by the user, blocks the email on the firewall and marks the status of the indicator as ‘Blocked’. The indicator is also linked to the record on which the playbook is triggered.          |
| 8       | Action - Email Address - Unblock(Indicator)         | Unblocks the indicators of type 'Email Address' on the firewall and marks the indicator as "Unblocked" based on its block status.                                                                                                           |
| 9       | Action - Email Address - Unblock(Specified by User) | Creates indicators for the email address specified by the user, unblocks the email on the firewall, and also marks the status of the indicator as Unblocked. The indicator is also linked to the record on which the playbook is triggered. |
| 10      | Action - File - Block (Indicator)                   | Blocks the indicators of type'File' on the firewall and marks the indicator as "Blocked" based on its block status.                                                                                                                         |
| 11      | Action - File - Block (Specified by user)           | Creates indicators for the file specified by the user, blocks the file on the firewall, and also marks the status of the indicator as blocked. The indicator is also linked to the record on which the playbook is triggered.               |
| 12      | Action - File MD5 - Block(Indicator)                | Blocks the indicators of type'Filehash' on the firewall and marks the indicator as "Blocked" based on its block status.                                                                                                                     |
| 13      | Action - File MD5 - Block(Specified by User)        | Creates indicators for the file hash specified by the user, blocks the indicator on the firewall, and also marks the status of the indicator as blocked. The indicator is also linked to the record on which the playbook is triggered.     |
| 14      | Action - File MD5- Unblock(Indicator)               | Unblocks the indicators of type'Filehash' on the firewall and marks the indicator as "Unblocked" based on its block status.                                                                                                                 |
| 15      | Action - File MD5 - Unblock(Specified by User)      | Creates indicators for the file hash specified by the user, unblocks the indicator on the firewall, and also marks the indicator as unblocked. The indicator is also linked to the record on which the playbook is triggered.               |
| 16      | Action - File - Unblock(Indicator)                  | Unblocks the indicators of type'File' on the firewall and marks the indicator as "Unblocked" based on its block status.                                                                                                                     |
| 17      | Action - File - Unblock(Specified by User)          | Creates indicators for the file specified by the user, unblocks the file on the firewall, and also marks the status of the indicator as unblocked. The indicator is also linked to the record on which the playbook is triggered.           |
| 18      | Action - Host - Block (Indicator)                   | Blocks indicators of type 'Host'on the firewall and marks the indicator as "Blocked" based on its block status.                                                                                                                             |
| 19      | Action - Host - Block (Specifiedby User)            | Creates indicators for the host specified by the user, blocks the host on the firewall, and also marks the indicator as blocked. The indicator is also linked to the record on which the playbook is triggered.                             |
| 20      | Action - Host - Isolate Host                        | Isolates indicators of type'Host' and marks the indicator as "Isolated" based on its block status.                                                                                                                                          |
| 21      | Action - Host - Unblock(Indicator)                  | Unblocks indicators of type'Host' on the firewall and marks the indicators as "Unblocked" based on their block status.                                                                                                                      |
| 22      | Action - Host - Unblock(Specified by User)          | Creates indicators for the host specified by the user, unblocks the host on the firewall, and also marks the indicator as Unblocked. The indicator is also linked to the record on which the playbook is triggered.                         |
| 23      | Action - IP Address - Block(Forticlient EMS)        | Quarantines endpoint with the specified IP address on FortiClient EMS.                                                                                                                                                                      |
| 24      | Action - IP Address - Block(Fortigate, FortiEDR)    | Isolates and blocks specified IP addresses using FortiGate and FortiEDR.                                                                                                                                                                    |
| 25      | Action - IP Address - Block(Indicator)              | Blocks indicators of type 'IPAddress' on the firewall and marks the indicators as "Blocked" based on their block status.                                                                                                                    |
| 26      | Action - IP Address - Block(Specified by User)      | Creates indicators for the specified IP Address', blocks the IP address on the firewall, and marks the indicators as blocked. The indicator is also linked to the record on which the playbook is triggered.                                |
| 27      | Action - IP Address - Unblock(Indicator)            | Unblocks indicators of type 'IPAddress' on the firewall and marks the indicator as "Unblocked" based on their block status.                                                                                                                 |
| 28      | Action - IP Address - Unblock(Specified by User)    | Creates indicators for the specified 'IP Address', unblocks the IP address on the firewall, and marks the indicators as unblocked. The indicator is also linked to the record on which the playbook is triggered.                           |
| 29      | Action (Type All) - BlockIndicators                 | Blocks all types of indicators on the firewall based on their block status.                                                                                                                                                                 |
| 30      | Action - URL - Block (Indicator)                    | Blocks indicators of type 'URL'on the firewall and marks the indicators as "Blocked" based on their block status.                                                                                                                           |
| 31      | Action - URL - Block (Specifiedby User)             | Creates indicators for the specified 'URL', blocks the URL on the firewall, and marks the indicator as blocked. The indicator is also linked to the record on which the playbook is triggered.                                              |
| 32      | Action - URL - Unblock(Indicator)                   | Unblocks indicators of type 'URL'on the firewall and marks the indicators as "Unblocked" based on their block status.                                                                                                                       |
| 33      | Action - URL - Unblock (Specifiedby User)           | Creates indicators for the specified 'URL', unblocks the URL on the firewall, and marks the indicator as unblocked. The indicator is also linked to the record on which the playbook is triggered.                                          |
| 34      | Alert - Disable Specific User                       | Disables the specified UserAccount from the Active Directory.                                                                                                                                                                               |
| 35      | Asset - Deploy Patch                                | Deploys the specified Patch on the selected asset using 'Microsoft SCCM'.                                                                                                                                                                   |
| 36      | Incident - Get Running Process                      | Retrieves details for all the running processes on the specified host.                                                                                                                                                                      |

## Hunt Playbook Collection

Playbooks in the *05-Hunt* collection automate threat hunting processes, search, and identify suspicious domains, malware, and other indicators in your environment and create alerts based on them.

### 05 - Hunt

Following is a table that lists the playbooks that are part of the “05-Hunt” collection in the Solution Pack:

| Sr. No. | Name of the playbook | Description                                                                                                           |
|---------|----------------------|-----------------------------------------------------------------------------------------------------------------------|
| 1       | Hunt Indicators      | Searches for the specified indicators in your environment using EDR tools, and create alerts for ones that are found. |

## Case Management Collection

This playbook collection has the following playbook

- 06 - IRP - Case Management

### 06 - IRP - Case Management 

| Sr. No | Name of the playbook                                                    | Description                                                                                                                                                                             |
|--------|-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1      | Alert - [01] Capture All SLA(Upon Create)                               | Updates the alert's acknowledgment due date and response due date based on the alert’s severity.                                                                                        |
| 2      | Alert - [02] Capture Ack SLA(Upon Update)                               | Updates the alert's acknowledgment date and SLA Status based on when the alert status is changed.                                                                                       |
| 3      | Alert - [03] Capture Response SLA(Upon Update)                          | Updates the alert's response date and SLA Status based on when the alert status is changed.                                                                                             |
| 4      | Alert - [04] Check for SLA violations                                   | Checks periodically for violations of acknowledgment SLA of the open alerts.                                                                                                            |
| 5      | Alert - [05] Update Ack and Response Due dates (Post Severity Change)   | Updates the alert’s acknowledgment due date and response due date for the change in the severity of alerts                                                                              |
| 6      | Alert - Close Corresponding SIEM Alert                                  | Closes the alert on the corresponding SIEM when an alert is closed in FortiSOAR.                                                                                                        |
| 7      | Alert - Periodic Update Alert SLAStatus                                 | This is a subroutine playbook to periodically check violations of acknowledgment and response SLA of the open alerts.                                                                   |
| 8      | Alert - Update SLA Details                                              | Updates an alert's acknowledgment due date and response due date based on the severity of the alert.                                                                                    |
| 9      | Approval - On Create                                                    | This playbook is triggered whenever an approval record is created, and an email is sent out to the intended approved(s).                                                                |
| 10     | Approval - On Email Receipt(Exchange)                                   | This playbook is triggered whenever an email is received via Exchange; the playbook determines whether the received email is an approval mail, and, if yes, checks its approval status. |
| 11     | Approval - On Email Receipt(IMAP)                                       | This playbook is triggered whenever an email is received via IMAP and it checks whether the received email is an approval mail along with its approval status.                          |
| 12     | Approval - On Email Receipt -Process Email                              | Checks if the email is an approval email and returns its approval status.                                                                                                               |
| 13     | Assign Random User to UnassignedAlerts                                  | Auto assigns alerts if their assignments were missed during alert creation.                                                                                                             |
| 14     | Assign Random User to UnassignedIncidents                               | Auto assigns incidents if their assignments were missing during incident creation.                                                                                                      |
| 15     | Fetch SLA Details                                                       | Fetches SLA Details for incidents as per Service, that is, for MSSP or Enterprise.                                                                                                      |
| 16     | Incident - [01] Capture All SLA(Upon Create)                            | Updates an alert acknowledgment due date and response due date based on the severity of the incident.                                                                                   |
| 17     | Incident - [02] Capture Ack SLA(Upon Update)                            | Updates an incident's acknowledgment date and SLA status when the status of the incident is changed.                                                                                    |
| 18     | Incident - [03] Capture ResponseSLA (Upon Update)                       | Update an incident's response date and SLA status when the status of the incident is changed.                                                                                           |
| 19     | Incident - [04] Check for SLA violations                                | Periodically check acknowledgment of SLA violations of the Open Incidents.                                                                                                              |
| 20     | Incident - [05] Update Response and Ack Due date (Post Severity Change) | Update an incident's acknowledgment due date and response due date following a change in severity.                                                                                      |
| 21     | Incident - Periodic UpdateIncident SLA Status                           | This is a subroutine playbook to check and update an incident’s SLA status.                                                                                                             |
| 22     | Incident (Post Create) PhaseChange                                      | Sets an incident's phase dates upon incident creation.                                                                                                                                  |
| 23     | Incident (Post Update) PhaseChange                                      | Updates an incident's phase dates when the incident phase is changed.                                                                                                                   |
| 24     | Incident - Set Phase Dates                                              | Updates an incident's phase dates based on the incident phase.                                                                                                                          |
| 25     | Incidents - Update SLA Details                                          | Updates an alert's acknowledgment due date and response due date based on incident severity.                                                                                            |
| 26     | Indicator - Check Expiry Status                                         | Checks periodically for the expiry date of the indicator and marks it as expired, if matched.                                                                                           |
| 27     | Indicator - Set Default ExpiryDate                                      | Sets the default expiry date when an indicator is created.                                                                                                                              |
| 28     | Indicator - Set First Seen Date                                         | Sets the first seen date when an indicator is created.                                                                                                                                  |
| 29     | Indicator - Set Last Seen Date                                          | Tracks the occurrence of an indicator by updating the last seen date.                                                                                                                   |
| 30     | Notify Blocked Indicator Statusto Linked Alerts                         | Adds a note about an indicator being blocked.                                                                                                                                           |
| 31     | Pause SLA - Alerts                                                      | Pauses the alert's acknowledgment or response when its respective SLA status is changed to'Awaiting Action'.                                                                            |
| 32     | Pause SLA - Incidents                                                   | Pauses the incident's acknowledgment or response SLA when its respective SLA status is changed to'Awaiting Action'.                                                                     |
| 33     | Prompt when Indicator linked is to Campaign                             | Notifies an analyst via manual input when an indicator is linked to a campaign.                                                                                                         |
| 34     | Set Prompt to an Alert                                                  | Displays a prompt on alerts when an indicator is linked to the campaign.                                                                                                                |

## 08 - Case Management (Extended)

| Playbook Name                                     | Description                                                                   |
|---------------------------------------------------|-------------------------------------------------------------------------------|
| Incident - [06] Check forAck SLA violations       | Notifies users of violation of Acknowledgement SLA.                           |
| Incident - [07] Check for Response SLA violations | Notifies users of violation of Response SLA.                                  |
| Notify Ack SLA Violation                          | Checks every 5 minutes, for Acknowledgement SLAviolations of open incidents.  |
| Notify Response SLA Violation                     | Checks every 5 minutes for Response SLA violations of acknowledged incidents. |

## 08 - Escalation

| Playbook Name                                | Description                                                                                            |
|----------------------------------------------|--------------------------------------------------------------------------------------------------------|
| Alert -Escalate To Incident                  | Escalates the selected alert to an incident.                                                           |
| Alert -Escalate To Incident (No Trigger)     | Creates a new incident with the specified inputs and links the alert(s) to the newly created incident. |
| Alert -Escalate to Incident (Link Relations) | Extractsrelated records and assigns them to a created incident.                                        |
| Resolve Alert                                | Marks the specified Security Alert as closed.                                                          |

## 08 - Similarity

| Playbook Name           | Description                                                      |
|-------------------------|------------------------------------------------------------------|
| Link Similar Alerts     | Links all selected similar alerts with the parent alert.         |
| Link Similar Emails     | Links all selected similar emails with the parent email.         |
| Link Similar Incidents  | Links all selected similar incidents with the parent incident.   |
| Link Similar Indicators | Links all selected similar indicators with the parent indicator. |

## 08 - SLA Management

| Playbook Name                                   | Description                                                                          |
|-------------------------------------------------|--------------------------------------------------------------------------------------|
| Alert - SetAssigned Date (upon creation)        | Updates the assigned date of the alert when a person is assigned to the alert.       |
| Alert - SetAssigned Date (upon reassignment)    | Updates the assigned date of the alert when a person is reassigned to the alert.     |
| Alert - SetResolved Date                        | Updates the resolved date of an alert when its state is marked as "Closed".          |
| Incident -Set Assigned Date (upon creation)     | Updates the assigned date of an incident when a lead is assigned to the incident.    |
| Incident -Set Assigned Date (upon reassignment) | Updates the assigned date of the incident when a lead is reassigned to the incident. |
| Incident -Set Resolved Date                     | Updates the resolved date of an incident when its state is marked as"Resolved".      |

## 08 - War Room Automation

| Playbook Name                             | Description                                                                                                                                                     |
|-------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CascadeOwnership for Newly Linked Records | Assigns war room responders as owners in all newly linked records such as alerts, incidents, indicators, etc.                                                   |
| GenerateWar Room Report                   | Generates aWar Room Report and adds a link to the specific War Room record as a comment.                                                                        |
| Notify NewAnnouncement                    | Sends an email notification to the war room owner and user owners whenever a new announcement is created.                                                       |
| NotifyNewly Linked Team                   | Sends an email notification to the new team that has been linked to the War Roomrecord.                                                                         |
| NotifyNewly Linked User(s)                | Sends an email notification to the new users that have been linked to the War Roomrecord.                                                                       |
| Send Email                                | This child playbook of Send Email Notification. It sends an email notification to war room owners and user owners related to any changes in the War Roomrecord. |
| Send EmailNotification                    | Fetchesdetails of War Room owners and user owners and sends them an email notification related to any changes in the war room record.                           |
| Send WarRoom Summary Email                | Generates and sends the War Room Summary report to the response team or specified user(s).                                                                      |
| Set WarRoom Live and Notify Responders    | Updates the war room status to "Live" and sends the email notification to the responders.                                                                       |
| Set up WarRoom from Alerts                | Establishes a War Room based on the selected alert(s).                                                                                                          |
| Set up WarRoom from Incidents             | Establishes a War Room based on the selected incident(s).                                                                                                       |
| Update WarRoom Close Date                 | Updates the ‘Close Date’ of the War Room record, when its status is marked as "Closed".                                                                         |

## Incident Response Playbook Collection

This collection has one playbook

- 09 - Incident response

### 09 - Incident Response

| Playbook Name                                        | Description                                                                                                                |
|------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
| Incident Response Plan (Type - Malware)              | Investigates incidents of type ‘Malware’ and executes the different phases of incident response using CarbonBlackResponse. |
| Incident Response Plan (Type - NIST 800-61 -Generic) | Creates tasks for incident response and handling as per the guidelines provided in NIST 800-61.                            |
| NIST 800-61 - Upfront Tasks                          | Creates tasks for incident response and handling as per the guidelines provided in NIST 800-61.                            |

## Utilities Playbook

This collection has one playbook.

- 10 - Utilities

### 10 - Utilities

You can use the playbooks in the *10 - Utilities* collection to perform various operations in FortiSOAR such as creating and linking assets to specified emails, alerts, or incidents, exporting all records or a specified module, or scheduling the health check of connectors and send appropriate notifications.

Following is a table that lists the playbooks that are part of the *10- Utilities* collection in the Solution Pack:

| Playbook Name                                 | Description                                                                                                                                                       |
|-----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Add Attacker Tag to Indicator (FortiDeceptor) | Finds the Attacker IP Address in a FortiDeceptoralert and adds the Attacker Tag to the indicator as well as updates the reputation of the indicator to Malicious. |
| Create and Link Asset                         | Creates an asset (if it doesn't exist already), and links it to the specified email, alert, or incident record.                                                   |
| Create and Link Indicator                     | Create an indicator (if it doesn't exist already), and link it to the specified email, alert, or incident record.                                                 |
| Download and Create Attachment                | Downloads the file from a specified URL and creates an attachment record for the same.                                                                            |
| Export as CSV                                 | Export all records of the given module with specified filters in the CSV format.                                                                                  |
| Get Paginated Records                         | Gets paginated records data and appends them in a.CSV file. This playbook is a reference playbook for 'Export as CSV'.                                            |
| Notify Connector Health Check Failures        | Scheduled to check connectors’ health status and notify the specified recipients of any failed health check.                                                      |
| Notify Failed Playbook Executions             | Notify specified recipients of any playbook failure. It can be scheduled to run at specific intervals.                                                            |
| Scheduled Configuration Export                | Export template name and email address to be updated in the 'Configuration' step. Can be used to schedule Configuration Export and send it as an email.           |

 

## Training Playbook Collection

This collection has one playbook.

- 12 - Training

### 12 -Training

| Playbook Name                               | Description                                                                                                                        |
|---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
| 01 - Investigate Filehash (Manual)          | This is a manually triggered playbook that the security analyst uses to determine the file hash reputation.                        |
| 02 - Investigate Filehash (Semi-Automated)  | This is a manually triggered playbook that investigates file hash reputation using VirusTotal.                                     |
| 03 - Investigate Filehash (Fully Automated) | Thisplaybook is triggered automatically following the creation of an alert; it investigates file hash reputation using VirusTotal. |

## Communication Playbook Collection

This collection has one playbook.

- 14 - Communications

### 14 - Communications

| Playbook Name                                | Description                                                                                                                              |
|----------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Add Note for Communication Linked            | Adds a note stating a new communication has been linked to the alert.                                                                    |
| Add Note for Communication Linked (Received) | Adds a note stating a new communication that was received has been linked to the alert.                                                  |
| Create Communication Record                  | Creates a record in the communications module and links it to an alert based on the information that is entered by the security analyst. |
| Create Communication Record (Email Reply)    | Creates a record in the communications module based on a reply to a received email.                                                      |
| Link Communication Record                    | Links the communication record to the corresponding alert based on the message ID.                                                       |
| Link Previous Communications                 | Links existing communications records to create a conversation thread.                                                                   |
| Manual Send Notification                     | Sends email notification for any selected communication record that is in either “Draft” or “Sending” state to the intended recipients.  |
| Send Notification                            | Sends auto-notification of any new communication record that is in the “Sending” state to the intended recipients.                       |