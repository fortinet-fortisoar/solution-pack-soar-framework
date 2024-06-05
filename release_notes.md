| [Home](./README.md) |
|---------------------|

# What's New

<table>
    <tr>
        <th>Compatible Version</th>
        <td>FortiSOAR v7.5.0 and later</td>
    </tr>
</table>

<table>
    <tr>
        <th>NOTE</th>
        <td>Before updating the SOAR Framework solution pack, make sure to back up any modifications you have made to <strong>System View Templates (SVTs)</strong>, <strong>Module Metadata (MMD)</strong>, and <strong>Playbooks</strong>. This is essential because updating the solution pack overwrites any changes you might have made.</td>
    </tr>
</table>

## Pre-Processing Rule
- Introduced new pre-processing rule to prevent file indicator creation when it is created without file attached to it

## Module Changes
### Incident Module
- Added the *Picklist as Phases* widget to the incident detailed view to show incident phase progress.
- Migrated *SLA Templates* module to **SLA Management** Solution Pack

## Playbook Changes
- Migrated below playbooks to **SOC Utilities** solution pack
    - 06 - IRP - Reporting > Export Selected Records
    - 08 - Utilities > Activate Inactive Users - Update User Status
    - 08 - Utilities > Activate Inactive Users
    - 08 - Utilities > Convert FortiSOAR User to SAML - Collect User Email IDs
    - 08 - Utilities > Convert FortiSOAR User to SAML - Update User Type

- Migrated below playbooks to **SLA Management** solution pack
    - Alert - [01] Capture All SLA (Upon Create)
    - Alert - [02] Capture Ack SLA (Upon Update)
    - Alert - [03] Capture Response SLA (Upon Update)
    - Alert - [04] Check for SLA violations
    - Alert - [05] Update Ack and Response Due dates (Post Severity Change)
    - Alert - Periodic Update Alert SLA Status
    - Alert - Update SLA Details
    - Fetch SLA Details
    - Incident - [01] Capture All SLA (Upon Create)
    - Incident - [02] Capture Ack SLA (Upon Update)
    - Incident - [03] Capture Response SLA (Upon Update)
    - Incident - [04] Check for SLA violations
    - Incident - [05] Update Response and Ack Due date (Post Severity Change)
    - Incident - [06] Check for Ack SLA violations
    - Incident - [07] Check for Response SLA violations
    - Incident - Periodic Update Incident SLA Status
    - Incidents - Update SLA Details
    - Notify Ack SLA Violation
    - Notify Response SLA Violation
    - Pause SLA - Alerts
    - Pause SLA - Incidents

## Extract Indicator Changes

Added functionality to extract indicators from new incidents
**Note-** Indicators will be extracted only from independently created incidents, not from escalated incidents.

    ### Newly Introduced Playbook: 
        - Extract Indicators (Incidents) 
        - Extract Indicators *renamed to* Extract Indicators (Alerts)

    ### Incident Module Change: 
    - Added a new fields 
        a. "Escalated" (picklist- YesNoInput)  
        b. "State" (picklist - Alert State) 
    - Added "Custom Picklist Widget" in Incident Detailed

    ### Global Variable: 
    -> Indicator_Type_Map
    - Incident Field Mapped for IOC Extraction:
    {
        "dLLName": "Process", 
        "filehash": "FileHash-MD5", 
        "processName": "Process", 
        "destinationIP": "IP Address", 
        "sourceIP": "IP Address", 
        "receipientEmailAddress": "Email Address" ,
        "targetAsset": "Host", 
        "senderDomain": "Domain", 
        "senderEmailAddress": "Email Address"
    }

    **Note -** Users need to manually append these values to the global variable.


    ### Added Key Store Records to replace existing global variables
        - Excludelist_Ports
        - Excludelist_Files
        - Excludelist_IPs
        - Excludelist_URLs
        - Excludelist_Domains


## Widgets Changes
Added 2 new widgets 
1. Picklist as Phases
2. SOAR Framework Configuration Wizard