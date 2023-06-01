| [Home](./README.md) |
|----------------------|

# What's New

|Compatible Version| FortiSOAR v7.2.2 and later|
|-|-|

## Playbook Enhancements

- Added following new playbooks to the mentioned collections:
    - The *Extract Indicators from Attachments* playbook in the collection *03 - Enrich* extracts indicators from attachments records linked to alerts of type *Suspicious Email* and *Phishing Email*
    - *Convert FortiSOAR User to SAML - Update User Type* to the collection *08 - Utilities*
    - *Convert FortiSOAR User to SAML - Collect User Email IDs* to the collection *08 - Utilities*
        These playbooks convert an existing FortiSOAR user to the SAML(SSO) user provided the user's *First Name*, *Last Name*, and *Email Address* in FortiSOAR&trade; are the same as that of the SAML provider.

- Renamed the *Fetch and Link Team to Related Records* playbook under the collection *08 - Utilities* to **Cascade Permissions to all Related Records**
- For the **Generate War Room Report** playbook under the collection *06 - IRP - War Room*, the **Generate Report** button now displays a loading icon until the report is generated
- For **Compute Alert Priority Weight (Post Update - Indicator Reputation Update)** and **Compute Alert Priority Weight (Post Indicator Extraction)** playbooks, under the collection *03 - Triage*, the record fetch limit in the `Find Related Alerts` step is now **5000**
- For the **Alert - Escalate To Incident (No Trigger)** playbook under the collection *06 - IRP - Case Management*, all the MITRE modules such as *Groups*, *Tactics*, *Software*, *Technique*, *Sub-Technique*, and *Mitigation* have been correlated to the incident from the escalated alert
- The **Alert - Close Corresponding SIEM Alert** playbook under the collection *06 - IRP - Case Management* requesting user action on their SIEM application, when an alert is closed, has now been replaced by the following comment:

    >The corresponding alert on SIEM has been closed.
    >
    >Replace "Add Closure Note" step in Alert - Close Corresponding SIEM Alert playbook to automate using a connector to accelerate the response time and better manage threat detection and response.

- Removed the **Link Similar Emails** playbook from the collection *06 - IRP - Case Management*

## Module Enhancements

### Connectors

The **Code Snippet** connector now comes pre-configured with a configuration named `SOAR Framework Default`

This default configuration has also been mapped in following playbooks:

- **Enrich Indicator (Type IP)** in the collection *03 - Enrich*
- **Ingest IOC From CSV File** in the collection *06 - IRP - Case Management*
- **Create Communication Record** in the collection *06 - IRP - Communications Tracking*
- **Export as CSV** in the collection *06 - IRP - Reporting*
- **Get Paginated Records** in the collection *06 - IRP - Reporting*

The connector comes with the following `python` packages:

- `dns`
- `pandas`
- `numpy`
- `json`
- `re`
- `csv`
- `arrow`

### Assets

- Added a new field named **Source Data**
- Renamed the *Related Record* tab to **Correlations** in *Asset* detailed view

### Alerts

- Added the **Event** module in the **Correlations** tab of the *Alert* detailed view
- Added the tooltips for the fields *IP Addresses* and *File Hashes*

### Indicators

- The *Enrichment Status* picklist has a new option named **Failed**

|NOTE|If you have updated any of the System View Templates(SVTs), Module Metadata (MMD), and playbooks, ensure to take a backup before updating SOAR Framework solution pack, as any changes that you have made will be overwritten.|
|-|-|


## Resolved Issues

- The **Cascade Permissions to all Related Records** playbook under the collection *08 - Utilities* works correctly when *IP Addresses* and *File Hashes* are populated in an alert record

- The **Enrich Indicator (Type All)** playbook under the collection *03 - Enrich* works correctly when executed as a reference playbook

- The **Escalate to Incident** playbook under the collection *06 - IRP - Case Management* now appropriately assigns tenants to incidents that were escalated from alerts