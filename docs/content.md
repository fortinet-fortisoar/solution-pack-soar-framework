# SOAR Framework Solution Pack

## Overview

The SOAR Framework Solution Pack provides you a snapshot of the configuration data and other items that can help you optimally use and experience FortiSOAR's incident response. 

This documentation provides a listing and brief description of the various types of modules, connectors, playbook collections, dashboards, reports, and widgets included in the Solution Pack.

Playbooks help perform various operations that automate security processes across an organization. These playbooks also help simulate use cases and provide training for FortiSOAR.

SOAR framework is a foundational Solution Pack that creates the day-to-day modules like alerts, incidents, indicators, campaigns, and hunts that Security Operations Center (SOC) requires.

**How to use all elements of FortiSOAR as per best practices**

## Prerequisites

SOAR Framework Solution Pack is the base solution pack there are no prerequisites to install it.

## Contents

This section lists the various contents of the SOAR Framework Solution Pack.

### Connector List

SOAR framework includes the following connectors:

***Create a table for these***

- Active Directory
- AlienVault-OTX
- CarbonBlack Response
- ElasticSearch
- Exchange
- Fortinet FortiClient EMS
- Fortinet FortiEDR
- Fortinet FortiGate
- Fortinet FortiSandbox
- Fortinet FortiSIEM
- Fortinet Web Filter Lookup
- IBM XForce
- IMAP
- IPStack
- MxToolbox
- NMAP Scanner
- SLA Calculator
- SSH
- ~~System Monitoring~~
- ThreatQ
- URLScan.io
- URLVoid

### Modules

The SOAR framework includes the following modules:

- Alerts
- Announcements
- Assets
- Campaigns
- Communication
- Events
- Hunt
- Incidents
- Indicators
- SLA Template
- War Rooms

#### Alerts

Alerts are primary actionable data elements that we obtain through a periodic ingestion process. We extract data through multiple channels like emails, SIEM platforms, or EDR platforms to create alerts. Once we have alerts, multiple playbooks are launched to extract and enrich the indicators.

##### Alert Ingestion

Running an alert through the system to find signs and understand if there was a threat is Alert Ingestion.

##### Indicator Extraction

Depends on the standard schema of the alerts module, which when populated, translates to the respective indicator record.

##### Indicator Enrichment

For every indicator, file URL, hash, domain, IP address, user; there is a corresponding enrichment playbook that goes through multiple intelligence platforms, and other processes, collects the data, and puts that information in a formatted manner to the indicator record.

#### Announcements

Announcements module helps notify users who are a part of a [war room](#war-rooms). 

#### Assets

Assets represent a unique piece of hardware and any information known about that hardware, such as MAC address, hostname, or IP address. Assets preferably have a unique identifier. The assets module helps add devices within FortiSOAR for use by the SOC team. Computers typically represent the assets of your organization. 

#### Campaigns

Campaigns are a collection of incidents relatable to a single threat actor. Many times, disparate incidents are connected attempts of a malicious attacker attempting to probe and gain access to a network.

#### Communication

It helps users to communicate with external entities like tenant contacts, and other SOC teams, using email, instant messaging (IM), etc. from within an alert generated in FortiSOAR. For this purpose, it uses IMAP and Exchange connectors.

#### Events

Events consist of records that contain machine-level information about activity that triggered a specific alert.

#### Hunt

The Hunts module is a place to store and organize your hunts. The hunt you create here will be the central repository where all Alerts, Assets, Users, and other modules’ records that become associated with your hunting activity will be linked together. 

#### Incidents

Incidents are confirmed alerts that negatively affect the confidentiality, integrity, and availability of an organization. Incidents represent a collection of information discovered during an Incident Response investigation. Incidents are triggered based on the suspicion or confirmation of a security breach.

#### Indicators

**Indicators of compromise** (IOCs) serve as evidence of probable intrusions on a host system or network. These artifacts help personnel at a Security Operations Center (SOC) to detect intrusion attempts or other malicious activities. IOCs help better analyze a particular malware’s techniques and behaviors and provide actionable threat intelligence to further improve an organization’s incident response strategies.

Some of this evidence of potential breach is found on event logs and timestamped entries in the system, applications, and services.

#### SLA Template

SLA Templates in FortiSOAR help create an in-built SLA management for incidents and alerts. For more information, please refer to [SLA Management](https://docs.fortinet.com/document/fortisoar/7.0.2/administration-guide/792686/sla-management). 

#### War Rooms

War Rooms in FortiSOAR is a collaborative space that enables SOC teams to mitigate a critical cyber threat scenario or campaign. FortiSOAR makes it easy for analysts to quickly and easily provision a War Room that allows participation of all stakeholders to analyze and collaborate to quickly mitigate the threat and restore the services. For more information, see the War Rooms chapter.

### Playbooks

SOAR Framework includes the following playbooks:

- 00 - Drafts (0)
- 01 - Ingest (0)
- 02 - Enrich (22)
- 02 - Enrich (Pluggable) (36)
- 03 - Triage (9)
- 04 - Use Cases (0)
- 05 - Actions (36)
- 06 - Hunt (1)
- 08 - Case Management (41)
- 08 - Case Management (Extended) (4)
- 08 - Escalation (4)
- 08 - Similarity (4)
- 08 - SLA Management (6)
- 08 - War Room Automation (12)
- 09 - Incident Response (3)
- 10 - Utilities (9)
- 11 - Demo (0)
- 12 - Training (3)
- 14 - Communications (8)

#### Naming Convention

Playbooks follow a specific order of execution and are arranged in the same sequence as the flow of alert ingestion in SOAR Framework. Hence the name carries a number that defines the order in which the playbooks run.

### Rules

Rules provide a framework to define a condition that generates notifications.

The SOAR Framework includes the following rules:

- Alert > Notify Creation - It sends a notification, via the app or the email, whenever an alert is **created**.
- Alert > Notify Update - It sends a notification, via the app or the email, whenever an alert is **updated**.
- Incident > Notify Creation - It sends a notification, via the app or the email, whenever an incident is **created**.
- Incident > Notify Update - It sends a notification, via the app or the email, whenever an incident is **updated**.

### Widgets

Widgets render information for the visual display inside View Template. Widget types vary such that specific widgets only correspond to certain view types. For example, the detail view has some exclusive widgets, such as Visual Correlation, Comments, Timeline, etc.

SOAR Framework has the following widgets:

- **Task Management (War Room)** - It is a comprehensive task management widget that helps users manage tasks and get visibility into the current task board.
- **Record Summary (War Room)** - It is primarily designed to showcase a particular record's highlights or summary, this widget houses multiple utility widgets within it to allow for customized uses.
- **SLA Count Down Timer** - This widget displays the remaining time for an SLA.
- **User Tile** - This widget shows relevant information like alerts, incidents, and tasks to users.
- **Incident Correlations** - This widget displays the correlation graph of an incident.

### Roles

SOAR framework has the following roles included:

- SOC Analyst
- SOC Manager

### Dashboards

A Dashboard is the default landing page, and users' home page, that users see when they log into FortiSOAR. Dashboard, at a glance, shows them the critical tasks on which they need to work. SOAR Framework includes the following dashboards:

- Overview
- ROI Summary
- SOC Admin
- Analyst
- System Health Status

### Reports

The reports module displays various reports for specific, defined users. SOAR framework includes the following reports:

- High Impact Incidents
- Incident Summary Report
- Overdue Alert Activities
- Overdue Incidents Activities
- Unhandled Activities
- War Room Summary Reports
- War Room Summary
- Weekly Alert Report
- Weekly IOC Report
- Weekly Incident Report

## Playbook Collection

The playbook collection is designed so that it runs in a specific order. Each collection has multiple playbooks with each containing tasks undertaken on each run.

### Enrich Playbook Collection

It has two playbook collections

- 02 - Enrich
- 02 - Enrich (Pluggable)

#### 02 - Enrich

| Playbook Name                            | Description                              |
| ---------------------------------------- | ---------------------------------------- |
| Asset - Get RunningProcess               | Retrieves a list of all processes that are running on the specified host. |
| Attachment - Get FileReputation          | Retrieves the reputation of a file that is submitted from FortiSOAR to VirusTotal. |
| Create Indicators (Batch)                | Creates indicator records in bulk.       |
| Extract Indicators - Manual              | Extracts and creates indicators from the specified alert records and then enriches specific fields in alerts with the indicator data. |
| Fotinet Fortisandbox (Get Reputation) - Get ScanResults | Retrieves the job verdict details for submitted samples based on the specified job ID. |
| Get Related IOCs For An IP               | Retrieves related IOCs for a specified IP address from threat intel sources. |
| Get Reputation After Specified Time      | Re-enriches indicators after a specified time. |
| Indicator (Manual Trigger)- Get LatestReputation | Retrieves the reputation of indicators using configured threat intelligence tools. You can trigger this playbook by manually selecting the indicator(s). |
| Indicator (Type All) - Get Latest Reputation | Based on the type of indicator, this playbook retrieves the reputation of indicators using configured threat intelligence tools. |
| Indicator (Type Domain) - Get Reputation | Retrieves the reputation of indicators of type‘Domain’ using configured threat intelligence tools. |
| Indicator (Type Email) - Get Reputation  | Retrieves the reputation of indicators of type ‘Email Address’ using configured threat intelligence tools. |
| Indicator (Type File) - Get Reputation   | Uploads a file to a sandbox and then retrieves its reputation using configured threat intelligence tools. |
| Indicator (Type File) - Get Reputation (FortinetSandbox) | Submits a file to Fortinet Sandbox and then retrieves its reputation. |
| Indicator (Type File - MD5) - Get Reputation | Retrieves the reputation of a file, identified by itsMD5 hash, using configured threat intelligence tools. |
| Indicator (Type Host) - Get Reputation   | Retrieves the reputation of indicators of type‘Host’ using configured threat intelligence tools. |
| Indicator (Type IP) - Get Reputation     | Retrieves the reputation of indicators of type ‘IPAddress’ using configured threat intelligence tools. |
| Indicator (Type Port) - Get Reputation   | Retrieves the reputation of indicators of type‘Port’ using configured threat intelligence tools. |
| Indicator (Type Process) - Get Reputation | Retrieves the reputation of indicators of type‘Process’ using configured threat intelligence tools. |
| Indicator (Type URL) - Get Reputation    | Retrieves the reputation of indicators of type ‘URL’ using configured threat intelligence tools. |
| Indicator (Type URL) - Get Reputation (FortinetSandbox) | Submit URL to Fortinet FortiSandbox.     |

#### 02 - Enrich (Pluggable)

| Playbook Name                            | Description                              |
| ---------------------------------------- | ---------------------------------------- |
| AlienValut OTX - File MD5Reputation      | Retrieves the reputation of indicators of type 'FileHash-MD5' using AlienValut OTX. |
| AlienValut OTX - IP Reputation           | Retrieves the reputation of indicators of type 'IPAddress' using AlienValut OTX. |
| AlienValut OTX - IP Reputation           | Retrieves the reputation of indicators of type 'IPAddress' using AlienValut OTX. |
| AlienValut OTX - URL Reputation          | Retrieves the reputation of indicators of type 'URL' using AlienValut OTX. |
| AlienVault-OTX - Domain Reputation       | Retrieves the reputation of indicators of type'Domain' using AlienValut OTX. |
| Anomali Threatstream - Domain Reputation | Retrieves the reputation of indicators of type'Domain' using Anomali Threatstream. |
| Anomali Threatstream - Email Reputation  | Retrieves the reputation of indicators of type 'Email' using Anomali Threatstream. |
| Anomali Threatstream - File MD5 Reputation | Retrieves the reputation of indicators of type'FileHash-MD5' using Anomali Threatstream. |
| Anomali Threatstream - IP Reputation     | Retrieves the reputation of indicators of type 'IPAddress' using Anomali Threatstream. |
| Anomali Threatstream - URL Reputation    | Retrieves the reputation of indicators of type 'URL' using Anomali Threatstream. |
| Cisco Threat Grid - File Reputation      | Submits a file to Cisco Threat Grid and then retrieves its reputation. |
| Fortinet Web Filter Lookup - Domain Reputation | Retrieves the reputation of indicators of type'Domain' using Fortinet Web Filter Lookup. |
| Fortinet Web Filter Lookup - URL Reputation | Retrieves the reputation of indicators of type 'URL' using Fortinet Web Filter Lookup. |
| IP Stack - Domain Geo Location           | Retrieves the geolocation of indicators of type'Domain' using IP Stack. |
| IP Stack - IP Reputation                 | Retrieves the geolocation of indicators of type 'IP Address' using IP Stack. |
| Indicator (Domain) - Get Latest Reputation | Retrieves the reputation of indicators of type'Domain' using configured threat intelligence playbooks. |
| Indicator (Email) - Get Latest Reputation | Retrieves the reputation of indicators of type 'Email' using configured threat intelligence playbooks. |
| Indicator (File MD5) - Get Latest Reputation | Retrieves the reputation of indicators of type'Filehash' using configured threat intelligence playbooks. |
| Indicator (File) - Get Latest Reputation | Uploads a file to a sandbox and then retrieves its reputation using configured threat intelligence tools playbooks. |
| Indicator (IP Address) - Get Latest Reputation | Retrieves the reputation of indicators of type 'IPAddress' using configured threat intelligence playbooks. |
| Indicator (Manual Trigger)- Get Latest Reputation | Retrieves the reputation of indicators using configured threat intelligence tools. You can trigger this playbook by manually selecting the indicator(s). |
| Indicator (Type All) - Get Latest Reputation | Based on the type of indicator, this playbook retrieves the reputation of indicators using configured threat intelligence tools. |
| Indicator (Type File - MD5) - Get Reputation | Retrieves the reputation of a file, identified by its MD5 hash, using configured threat intelligence tools. |
| Indicator (Type Host) - Get Latest Reputation | Retrieves the reputation of indicators of type'Host' using configured threat intelligence playbooks. |
| Indicator (Type Process) - Get Latest Reputation | Retrieves the reputation of indicators of type'Process' using configured threat intelligence tools. |
| Indicator (URL) - Get the latest Reputation | Retrieves the reputation of indicators of type 'URL' using configured threat intelligence playbooks. |
| MXToolBox - IP Reputation                | Retrieves the reputation of indicators of type 'IPAddress' using MXToolBox. |
| Symantec Deepsight Intelligence - File MD5Reputation | Retrieves the reputation of a file, identified by its MD5 hash, using Symantec DeepSight Intelligence. |
| ThreatQ - Email Reputation               | Retrieves the reputation of indicators of type 'Email' using ThreatQ. |
| URLVoid - Domain Reputation              | Retrieves the reputation of indicators of type'Domain' using URLVoid. |
| URLVoid - URL Reputation                 | Retrieves the reputation of indicators of type 'URL' using URLVoid. |
| VirusTotal - Domain Reputation           | Retrieves the reputation of indicators of type'Domain' using VirusTotal. |
| VirusTotal - URL Reputation              | Retrieves the reputation of indicators of type 'URL' using VirusTotal. |
| Virustotal - File MD5 Reputation         | Retrieves the reputation of indicators of type 'File Hash MD5' using VirusTotal. |
| Virustotal - File Reputation             | Submits a file to VirusTotal and then retrieves its reputation. |
| Virustotal - IP Reputation               | Retrieves the reputation of indicators of type 'IP Address' using VirusTotal. |
| Whois - IP Reputation                    | Retrieves whois data for indicators of type 'IPAddress' using Whois RDAP. |

### Triaging Playbook Collection

This playbook collection appears with the name 

- 03 - Triage

#### 03 - Triage

| Playbook Name                            | Description                              |
| ---------------------------------------- | ---------------------------------------- |
| Compute Alert PriorityWeight (Post Update) | Computes and sets the priority weight for an alert, when the alert is updated. The priority weight is calculated based on indicators related to the alert. |
| Compute Alert Priority Weight (Post Update -Indicator Linked) | Computes and sets the priority weight for an alert, when an indicator related to the alert is updated. The priority weight is calculated based on indicators related to the alert. |
| Compute Alert Priority Weight (Post Update -Indicator Reputation Update) | Computes and sets the priority weight for an alert, when the reputation of an indicator is updated. The priority weight is calculated based on indicators related to the alert. |
| Find and Relate Similar Alerts           | Finds similar alerts based on the filter criteria you have specified and adds correlations to similar alerts. |
| Find and Relate Similar Alerts - ML      | Finds similar alerts based on the filter criteria you have specified and adds correlations to similar alerts using the recommendation APIs (ML). |
| Flag Indicators Linked across multiple alerts | Flags changes made in indicators that are linked to multiple alerts. |
| Map Historical Alerts and Escalate for malicious Indicators | Creates a mapping for historical alerts and then escalates the alerts to incidents if malicious indicators are found in the historical alerts. If the incident already exists, then the information is updated into the incident; else a new incident is created. |
| Prioritize Alerts With VIP Assets        | Raises the severity of the alert if it is associated with a supercritical asset. |
| Update Alert Severity for Malicious Indicators | Sets the severity of the alert to ‘Critical’ if its associated indicators are found to be ‘malicious’. |

### Actions Playbook Collection

This playbook collection appears with the name

- 05 - Actions

#### 05 - Actions

| Playbook Name                            | Description                              |
| ---------------------------------------- | ---------------------------------------- |
| Action -Asset Mitigation                 | Carries out a sequence of processes such as Clean Asset, AV scan, etc. to decide whether to keep an asset in isolation or remove it from isolation. |
| Action - Domain - Block (Indicator)      | Blocks the indicators of type 'Domain' on the firewall and marks the indicator as "Blocked" based on its Block status. |
| Action - Domain - Block (Specified by User) | Creates an indicator for the domain name specified by the user, blocks the domain on the firewall, and also marks the status of the indicator 'Blocked’. The indicator is also linked to the record on which the playbook is triggered. |
| Action - Domain - Unblock (Indicator)    | Unblocks the indicators of type 'Domain' on the firewall and marks the indicator as "Unblocked" based on its block status. |
| Action - Domain - Unblock (Specified by User) | Creates indicator for the domain name specified by the user, unblocks the domain on the firewall, and also marks the status of the indicator as ‘Unblocked’. The indicator is also linked to the record on which the playbook is triggered. |
| Action - Email Address - Block (Indicator) | Blocks the indicators of type 'Email Address' on the firewall and marks indicator as "Blocked" based on its block status. |
| Action - Email Address - Block (Specified by User) | Creates indicator for the email address specified by the user, blocks the email on the firewall, and marks the status of the indicator as ‘Blocked’. The indicator is also linked to the record on which the playbook is triggered. |
| Action - Email Address - Unblock (Indicator) | Unblocks the indicators of type 'Email Address' on the firewall and mark indicator as "Unblocked" based on its block status. |
| Action - Email Address - Unblock (Specified by user) | Creates indicators for the email address specified by the user, unblocks the email on the firewall, and also marks the status of the indicator as Unblocked. The indicator is also linked to the record on which the playbook is triggered. |
| Action - File - Block (Indicator)        | Blocks the indicators of type 'File' on the firewall and marks the indicator as "Blocked" based on its block status. |
| Action - File - Block (Specified by User) | Creates indicators for the file specified by the user, blocks the file on the firewall, and also marks the status of the indicator as blocked. The indicator is also linked to the record on which the playbook is triggered. |
| Action - File MD5 - Block (Indicator)    | Blocks the indicators of type 'Filehash' on the firewall and marks the indicator as "Blocked" based on its block status. |
| Action - File MD5 - Block (Specified by User) | Creates indicators for the file hash specified by the user, blocks the indicator on the firewall, and also marks the status of the indicator as blocked. The indicator is also linked to the record on which the playbook is triggered. |
| Action - File MD5- Unblock (Indicator)   | Unblocks the indicators of type 'Filehash' on the firewall and marks the indicator as "Unblocked" based on its block status. |
| Action - File MD5 - Unblock (Specified by User) | Creates indicators for the file hash specified by the user, unblocks the indicator on the firewall, and also marks the indicator as unblocked. The indicator is also linked to the record on which the playbook is triggered. |
| Action - File - Unblock (Indicator)      | Unblocks the indicators of type 'File' on the firewall and marks the indicator as "Unblocked" based on its block status. |
| Action - File - Unblock (Specified by User) | Creates indicators for the file specified by the user, unblocks the file on the firewall, and also marks the status of the indicator as unblocked. The indicator is also linked to the record on which the playbook is triggered. |
| Action - Host - Block (Indicator)        | Blocks indicators of type 'Host' on the firewall and marks the indicator as "Blocked" based on its block status. |
| Action - Host - Block (Specified by User) | Creates indicators for the host specified by the user, blocks the host on the firewall, and also marks the indicator as blocked. The indicator is also linked to the record on which the playbook is triggered. |
| Action - Host - Isolate Host             | Isolates indicators of type 'Host' and marks the indicator as "Isolated" based on its block status. |
| Action - Host - Unblock (Indicator)      | Unblocks indicators of type 'Host' on the firewall and marks the indicators as "Unblocked" based on their block status. |
| Action - Host - Unblock (Specified by User) | Creates indicators for the host specified by the user, unblocks the host on the firewall, and also marks the indicator as unblocked. The indicator is also linked to the record on which the playbook is triggered. |
| Action - IP Address - Block (Forticlient EMS) | Quarantines endpoint with the specified IP address on FortiClient EMS. |
| Action - IP Address - Block (Fortigate, FortiEDR) | Isolates and blocks specified IP addresses using FortiGate and FortiEDR. |

| Action - IP Address - Block (Indicator)  | Blocks indicators of type 'IP Address' on the firewall and marks the indicators as "Blocked" based on their block status.
| Action - IP Address - Block (Specified by User) | Creates indicators for the specified IP Address', blocks the IP address on the firewall, and marks the indicators as blocked. The indicator is also linked to the record on which the playbook is triggered. |
| Action - IP Address - Unblock (Indicator) | Unblocks indicators of type 'IP Address' on the firewall and marks the indicator as "Unblocked" based on their block status. |
| Action - IP Address - Unblock (Specified by User) | Creates indicators for the specified 'IP Address', unblock the IP address on the firewall, and marks the indicators as unblocked. The indicator is also linked to the record on which the playbook is triggered. |
| Action (Type All) - Block Indicators     | Blocks all types of indicators on the firewall based on their block status. |
| Action - URL - Block (Indicator)         | Blocks indicators of type 'URL' on the firewall and marks the indicators as "Blocked" based on their block status. |
| Action - URL - Block (Specified by User) | Creates indicators for the specified 'URL', blocks the URL on the firewall, and marks the indicator as blocked. The indicator is also linked to the record on which the playbook is triggered. |
| Action - URL - Unblock (Indicator)       | Unblocks indicators of type 'URL' on the firewall and marks the indicators as "Unblocked" based on their block status. |
| Action - URL - Unblock (Specified by User) | Creates indicators for the specified 'URL', unblocks the URL on the firewall, and marks the indicator as unblocked. The indicator is also linked to the record on which the playbook is triggered. |
| Alert - Disable Specific User            | Disables the specified User Account from the active Directory. |
| Asset - Deploy Patch                     | Deploys the specified Patch on the selected asset using 'Microsoft SCCM'. |
| Incident - Get Running Process           | Retrieves details for all the running processes on the specified host. |

### Hunt Playbook Collection

This collection has one playbook

- Hunt Indicators - It searches for the specified indicators in your environment using EDR tools, and creates alerts for ones that are found.

### Case Management Collection

This playbook collection has 2 playbooks

- 08 - Case Management
- 08 - Case Management (Extended)
- 08 - Escalation
- 08 - Similarity
- 08 - SLA Management
- 08 - War Room Automation

#### 08 - Case Management

| Playbook Name                            | Description                              |
| ---------------------------------------- | ---------------------------------------- |
| Add a User to the OwnersList             | Checks if the specified module is user ownable, and then adds the selected user as an owner of the record/records irrespective of which team the user belongs to. |
| Alert - [01] Capture All SLA (Upon Create) | Updates the alert's acknowledgment due date and response due date based on the alert’s severity. |
| Alert - [02] Capture Ack SLA (Upon Update) | Updates the alert's acknowledgment date and SLAStatus based on when the alert status is changed. |
| Alert - [03] Capture Response SLA (Upon Update) | Updates the alert's response date and SLA Status based on when the alert status is changed. |
| Alert - [04] Check for SLA violations    | Checks periodically for violations of acknowledgment SLA of the open alerts. |
| Alert - [05] Update Ack and Response Due dates(Post Severity Change) | Updates the alert’s due date for acknowledgment and response for the change in the severity of alerts |
| Alert - Close Corresponding SIEM Alert   | Closes the alert on the corresponding SIEM when an alert is closed in FortiSOAR. |
| Alert - Periodic Update Alert SLA Status | This is a subroutine playbook to periodically check violations of acknowledgment and response SLA of the open alerts. |
| Alert - Set Metrics (Upon Close)         | Calculates queued and resolution time for a closed alert. |
| Alert - Update SLA Details               | Updates an alert's acknowledgment and response due dates based on the severity of the alert. |
| Approval - On Create                     | Thisplaybook is triggered whenever an approval record is created, and an email is sent out to the intended approver(s). |
| Approval - On Email Receipt (Exchange)   | This playbook is triggered whenever an email is received via Exchange; the playbook determines whether the received email is an approval mail, and, if yes, checks its approval status. |
| Approval - On Email Receipt (IMAP)       | This playbook is triggered whenever an email is received via IMAP and it checks whether the received email is an approval mail along with its approval status. |
| Approval - On Email Receipt - Process Email | Checks if the email is an approval email and returns its approval status. |
| Assign Random User to Unassigned Alerts  | Auto assigns alerts if their assignments were missed during alert creation. |
| Assign Random User to Unassigned Incidents | Auto assigns incidents if their assignments were missing during incident creation. |
| Escalated Alert - Copy Related Records to Incidents | Links related data from the alert to the incident, when an alert is escalated. |
| Escalated Alert - Related Asset Records to Incidents | Links related assets from the alert to the incident, when an alert is escalated. |
| Export Selected Records                  | Exports all selected records to a JSON file and creates an attachment record for the same. |
| Fetch SLA Details                        | Fetches SLA Details for incidents as per Service, that is, for MSSP or Enterprise. |
| Import Data                              | Imports a valid JSON file to a relevant module and creates subsequent records. |
| Incident - [01] Capture All SLA (Upon Create) | Updates an alert's acknowledgment and response due dates based on the severity of the incident. |
| Incident - [02] Capture Ack SLA (Upon Update) | Updates an incident's acknowledgment date and SLAstatus when the status of the incident is changed. |
| Incident - [03] Capture Response SLA (Upon Update) | Update an incident's response date and SLA status when the status of the incident is changed. |
| Incident - [04] Check for SLA violations | Periodically check Acknowledgement SLA violations of the Open Incidents. |
| Incident - [05] Update Response and Ack Due date(Post Severity Change) | Update an incident's acknowledgment and response due dates following a change in severity. |
| Incident - Periodic Update Incident SLA Status | This is a subroutine playbook to check and update an incident’s SLA status. |
| Incident (Post Create) Phase Change      | Sets an incident's phase dates upon incident creation. |
| Incident (Post Update) Phase Change      | Updates an incident's phase dates when the incident phase is changed. |
| Incident - Set Phase Dates               | Updates an incident's phase dates based on the incident phase. |
| Incident Summary Notification            | Sends a daily summary of incidents created and closed. |
| Incidents - Update SLA Details           | Updates an alert's acknowledgment and response due dates based on incident severity. |
| Indicator - Check Expiry Status          | Checks periodically for the expiry date of the indicator and marks it as expired, if matched. |
| Indicator - Set Default Expiry Date      | Sets the default expiry date when an indicator is created. |
| Indicator - Set First Seen Date          | Sets the first seen date when an indicator is created. |
| Indicator - Set Last Seen Date           | Tracks the occurrence of an indicator by updating the last seen date. |
| Notify Blocked Indicator Status to Linked Alerts | Adds a note about an indicator being blocked. |
| Pause SLA - Alerts                       | Pauses the alert's acknowledgment or response when its respective SLA status is changed to 'Awaiting Action'. |
| Pause SLA - Incidents                    | Pauses the incident's acknowledgment or response SLA when its respective SLA status is changed to 'Awaiting Action'. |
| Prompt when Indicator linked is to Campaign | Notifies an analyst via manual input when an indicator is linked to a campaign. |
| Set Prompt to an Alert                   | Displays a prompt on alerts when an indicator is linked to the campaign. |

#### 08 - Case Management (Extended)

| Playbook Name                            | Description                              |
| ---------------------------------------- | ---------------------------------------- |
| Incident - [06] Check forAck SLA violations | Notifies users of violation of Acknowledgement SLA. |
| Incident - [07] Check for Response SLA violations | Notifies users of violation of Response SLA. |
| Notify Ack SLA Violation                 | Checks every 5 minutes, for Acknowledgement SLAviolations of open incidents. |
| Notify Response SLA Violation            | Checks every 5 minutes for Response SLA violations of acknowledged incidents. |

#### 08 - Escalation

| **Playbook Name**                        | **Description**                          |
| ---------------------------------------- | ---------------------------------------- |
| Alert -Escalate To Incident              | Escalates the selected alert to an incident. |
| Alert -Escalate To Incident (No Trigger) | Creates a new incident with the specified inputs and links the alert(s) to the newly created incident. |
| Alert -Escalate to Incident (Link Relations) | Extractsrelated records and assigns them to a created incident. |
| Resolve Alert                            | Marks the specified Security Alert as closed. |

#### 08 - Similarity

| **Playbook Name**       | **Description**                          |
| ----------------------- | ---------------------------------------- |
| Link Similar Alerts     | Links all selected similar alerts with the parent alert. |
| Link Similar Emails     | Links all selected similar emails with the parent email. |
| Link Similar Incidents  | Links all selected similar incidents with the parent incident. |
| Link Similar Indicators | Links all selected similar indicators with the parent indicator. |

#### 08 - SLA Management

| **Playbook Name**                        | **Description**                          |
| ---------------------------------------- | ---------------------------------------- |
| Alert - SetAssigned Date (upon creation) | Updates the assigned date of the alert when a person is assigned to the alert. |
| Alert - SetAssigned Date (upon reassignment) | Updates the assigned date of the alert when a person is reassigned to the alert. |
| Alert - SetResolved Date                 | Updates the resolved date of an alert when its state is marked as "Closed". |
| Incident -Set Assigned Date (upon creation) | Updates the assigned date of an incident when a lead is assigned to the incident. |
| Incident -Set Assigned Date (upon reassignment) | Updates the assigned date of the incident when a lead is reassigned to the incident. |
| Incident -Set Resolved Date              | Updates the resolved date of an incident when its state is marked as"Resolved". |

#### 08 - War Room Automation

| **Playbook Name**                        | **Description**                          |
| ---------------------------------------- | ---------------------------------------- |
| CascadeOwnership for Newly Linked Records | Assigns war room responders as owners in all newly linked records such as alerts, incidents, indicators, etc. |
| GenerateWar Room Report                  | Generates aWar Room Report and adds a link to the specific War Room record as a comment. |
| Notify NewAnnouncement                   | Sends an email notification to the war room owner and user owners whenever a new announcement is created. |
| NotifyNewly Linked Team                  | Sends an email notification to the new team that has been linked to the War Roomrecord. |
| NotifyNewly Linked User(s)               | Sends an email notification to the new users that have been linked to the War Roomrecord. |
| Send Email                               | This child playbook of Send Email Notification. It sends an email notification to war room owners and user owners related to any changes in the War Roomrecord. |
| Send EmailNotification                   | Fetchesdetails of War Room owners and user owners and sends them an email notification related to any changes in the war room record. |
| Send WarRoom Summary Email               | Generates and sends the War Room Summary report to the response team or specified user(s). |
| Set WarRoom Live and Notify Responders   | Updates the war room status to "Live" and sends the email notification to the responders. |
| Set up WarRoom from Alerts               | Establishes a War Room based on the selected alert(s). |
| Set up WarRoom from Incidents            | Establishes a War Room based on the selected incident(s). |
| Update WarRoom Close Date                | Updates the ‘Close Date’ of the War Room record, when its status is marked as "Closed". |

### Incident Response Playbook Collection

This collection has one playbook

- 09 - Incident response

#### 09 - Incident Response

| Playbook Name                            | Description                              |
| ---------------------------------------- | ---------------------------------------- |
| Incident Response Plan (Type - Malware)  | Investigates incidents of type ‘Malware’ and executes the different phases of incident response using CarbonBlackResponse. |
| Incident Response Plan (Type - NIST 800-61 -Generic) | Creates tasks for incident response and handling as per the guidelines provided in NIST 800-61. |
| NIST 800-61 - Upfront Tasks              | Creates tasks for incident response and handling as per the guidelines provided in NIST 800-61. |

### Utilities Playbook

This collection has one playbook.

- 10 - Utilities

#### 10 - Utilities

You can use the playbooks in the *10 -* *Utilities* collection to perform various operations in FortiSOAR such as creating and linking assets to specified emails, alerts, or incidents, exporting all records or a specified module, or scheduling the health check of connectors and send appropriate notifications.

Following is a table that lists the playbooks that are part of the *“10- Utilities”* collection in the Solution Pack:

| Playbook Name                            | Description                              |
| ---------------------------------------- | ---------------------------------------- |
| Add Attacker Tag to Indicator (FortiDeceptor) | Finds the Attacker IP Address in a FortiDeceptoralert and adds the Attacker Tag to the indicator as well as updates the reputation of the indicator to Malicious. |
| Create and Link Asset                    | Creates an asset (if it doesn't exist already), and links it to the specified email, alert, or incident record. |
| Create and Link Indicator                | Create an indicator (if it doesn't exist already), and link it to the specified email, alert, or incident record. |
| Download and Create Attachment           | Downloads the file from a specified URL and creates an attachment record for the same. |
| Export as CSV                            | Export all records of the given module with specified filters in the CSV format. |
| Get Paginated Records                    | Gets paginated records data and appends them in a.CSV file. This playbook is a reference playbook for 'Export as CSV'. |
| Notify Connector Health Check Failures   | Scheduled to check connectors’ health status and notify the specified recipients of any failed health check. |
| Notify Failed Playbook Executions        | Notify specified recipients of any playbook failure. It can be scheduled to run at specific intervals. |
| Scheduled Configuration Export           | Export template name and email address to be updated in the 'Configuration' step. Can be used to schedule Configuration Export and send as email. |

 

### Training Playbook Collection

This collection has one playbook.

- 12 - Training

#### 12 -Training

| Playbook Name                            | Description                              |
| ---------------------------------------- | ---------------------------------------- |
| 01 - Investigate Filehash (Manual)       | This is a manually triggered playbook that the security analyst uses to determine the file hash reputation. |
| 02 - Investigate Filehash (Semi-Automated) | This is a manually triggered playbook that investigates file hash reputation using VirusTotal. |
| 03 - Investigate Filehash (Fully Automated) | Thisplaybook is triggered automatically following the creation of an alert; it investigates file hash reputation using VirusTotal. |

### Communication Playbook Collection

This collection has one playbook.

- 14 - Communications

#### 14 - Communications

| Playbook Name                            | Description                              |
| ---------------------------------------- | ---------------------------------------- |
| Add Note for Communication Linked        | Adds a note stating a new communication has been linked to alert. |
| Add Note for Communication Linked (Received) | Adds a note stating a new communication that was received has been linked to alert. |
| Create Communication Record              | Creates a record in the communications module and links it to an alert based on the information that is entered by the security analyst. |
| Create Communication Record (Email Reply) | Creates a record in the communications module based on a reply to a received email. |
| Link Communication Record                | Links the communication record to the corresponding alert based on the message ID. |
| Link Previous Communications             | Links existing communications records to create a conversation thread. |
| Manual Send Notification                 | Sends email notification for any selected communication record that is in either “Draft” or “Sending” state to the intended recipients. |
| Send Notification                        | Sends auto-notification of any new communication record that is in the “Sending” state to the intended recipients. |

## Scenario Flow

The FortiSOAR process happens in multiple steps where an alert is ingested, indicators extracted and enriched, multiple playbooks are executed to analyze and understand if the alerts contain sufficient information to compile and report as an incident.

![](assets/Fortisoar-Flow.png)

This flow diagram is explained in the following 

1. **Pull alerts from an alert source** - FortiSOAR, at regular intervals, pulls alerts from an alert source like a SIEM or an EDR. It combines threats or alerts from multiple sources into a single location.
2. **Extract indicators from alerts** - Indicators, like IP address, email address, or any such identifiable information that is associated with the alert source, are extracted to gather more context or information related to the alert.
3. **Playbooks Execution** - FortiSOAR has multiple playbooks that run to automate and expedite the process of notification or case management, Triaging, Investigation, and possible escalation. Following are some of the tasks that playbooks have automated.
   1. **Enrich Indicators** - The indicator enrichment process helps collect more actionable information for the SOC analyst. E.g. fetching the reputation of a suspicious file, domain, or a URL from threat intelligence platforms like Anomali or VirusTotal.
   2. **Triage** - You can sort, systemize, or perform computation on the enriched data to reduce investigation time. A thorough investigation in a shorter time helps make a decision and reach a resolution faster.
   3. **Action** - After a successful triage, playbooks help take corrective action on the triaged indicators. Actions may include asset mitigation by isolation, blocking domains and URLs through firewalls, and blocking or disabling users and IP addresses.
   4. **Hunt** - Hunt playbooks search and identify suspicious domains, malware, files, or other indicators and create alerts as and when such threats are located.
   5. **Case Management** - Case Management playbooks automate processes like adding users as case owners, tracking SLA and resolution timelines, among other things. It also contains playbooks that resolve an alert by taking appropriate action or marking it as an 'incident' and escalating it.
   6. **Incident Response** - These playbooks help plan response to an incident like a malware attack.
