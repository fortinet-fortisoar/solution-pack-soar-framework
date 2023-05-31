| [Home](./README.md) |
|----------------------|

# What's New

>**Compatible Version**: FortiSOAR v7.2.2 and later

## Playbook Enhancements

- Added following new playbooks to the mentioned collections:
    - *Extract Indicators from Attachments* to the collection *03 - Enrich* to extract indicators from an email attachment
    - *Convert FortiSOAR User to SAML - Update User Type* to the collection *08 - Utilities*
    - *Convert FortiSOAR User to SAML - Collect User Email IDs* to the collection *08 - Utilities*
        These playbooks covert an existing FortiSOAR user to the SAML(SSO) user
- Renamed the *Fetch and Link Team to Related Records* playbook under the collection *08 - Utilities* to **Cascade Permissions to all Related Records**
- For the **Generate War Room Report** playbook under the collection *06 - IRP - War Room*, the **Generate Report** button now displays a loading icon until the report is generated
- For the the **Compute Alert Priority Weight (Post Update - Indicator Reputation Update)** playbook under the collection *03 - Triage*, the record fetch limit in the `Find Related Alerts` step is now **5000**
- For the **Alert - Escalate To Incident (No Trigger)** playbook under the collection *06 - IRP - Case Management*, all the MITRE modules such as *Groups*, *Tactics*, *Software*, *Technique*, *Sub-Technique*, and *Mitigation* have been correlated to the incident from the escalated alert
- An input requesting comment now replaces the manual input notification for the **Alert - Close Corresponding SIEM Alert** playbook under the collection *06 - IRP - Case Management*
- Removed the **Link Similar Emails** playbook from the collection *06 - IRP - Case Management*

## Module Enhancements

- **Assets**
    - Added a new field named **Source Data**
    - Renamed the *Related Record* tab to **Correlations** in *Asset* detailed view

- **Alerts**
    - Added the **Event** module in the **Correlations** tab of the *Alert* detailed view
    - Added the tooltips for the fields *IP Addresses* and *File Hashes*

- **Indicators**
    - The *Enrichment Status* picklist has a new option named **Failed**

- **SLA Template**
    - Added a new field named **Restart SLA**
        - This checkbox helps user to choose how response SLA is calculated for an alert or incident
        - Once `Acknowledge SLA` is set for the alert or incident record, this field gives option user to calculate `Response SLA` from `Created Date` or `Acknowledge Date`
        - For example, if **Restart SLA** is checked, then `Response Due Date` will be calculated start from time when `Acknowledge SLA` was set otherwise `Response Due Date` will be calculated from `Created Date` of the record

## Resolved Issues

- The **Fetch and Link Team to Related Records** playbook under the collection *08 - Utilities* works correctly when *IP Addresses* and *File Hashes* are populated in an alert record
- The **Enrich Indicator (Type All)** playbook under the collection *03 - Enrich* works correctly when executed as a reference playbook