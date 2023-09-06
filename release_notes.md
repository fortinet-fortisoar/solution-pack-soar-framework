| [Home](./README.md) |
|----------------------|

# What's New

| Compatible Version | FortiSOAR v7.4.1 and later |
|--------------------|----------------------------|

| NOTE | If you have updated any of the System View Templates(SVTs), Module Metadata (MMD), and playbooks, ensure to take a backup before updating SOAR Framework solution pack, as any changes that you have made will be overwritten. |
|------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

## Playbook Enhancements

- The **Find and Relate Similar Alerts** playbook in the *03 - Triage* collection now finds alerts for the last 30 days and in MSSP env it finds alerts belonging to the same tenant the playbook executing on.
- The **Flag Indicators Linked Across Multiple Alerts** playbook in the *03 - Triage* collection now flags to only those alerts that were generated in the last 30 days.

## Module Enhancements

### Indicators
- `TLP`, `Expired` and `Expired On` fields in the indicator module have been marked by default replicable from the tenant node in the MSSP environment 

### Key Store
- Introduced new fields named `JSON Value` and `Notes`

### Assets

Rearranged the Asset List View Columns. The sequence of Asset fields in the list view is as following

- Id
- Display Name
- Hostname
- MAC Address
- IP Address
- Device UUID
- Vendor
- Product
- Category
- Asset Criticality
- Asset State
- Asset Status
- Asset Risk
- Asset Registration Date
- Last Scanned On
- Property Of

### Incidents
- Added `Technique ID` field to the `Incident` Module detailed view

## Dashboard Enhancements

### Analyst Dashboard
-  In the `Analyst` dashboard's Critical Alerts Tab, updated the display condition to show only high and critical severity alerts.