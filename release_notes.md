| [Home](./README.md) |
|----------------------|

# What's New

>**Compatible Version**: FortiSOAR v7.2.2 and later

## Playbook Enhancements

- For the *Generate War Room Report* playbook under the collection *06 - IRP - War Room*, the **Generate Report** button now displays a loading icon until the report is generated
- Removed the **Link Similar Emails** playbook under the collection *06 - IRP - Case Management*

## Module Enhancements

- **Assets**
    - Added a new field named **Source Data**
    - Renamed the *Related Record* tab to **Correlations** in *Asset* detailed view

- **Alerts**
    - Added the **Event** module in the **Correlations** tab of the *Alert* detailed view
    - Added the tooltips for the fields *IP Addresses* and *File Hashes*

- **Indicators**
    - The *Enrichment Status* picklist has a new option named **Failed**

## Resolved Issues

- The **Fetch and Link Team to Related Records** playbook under the collection *08 - Utilities* works correctly when *IP Addresses* and *File Hashes* are populated in an alert record 