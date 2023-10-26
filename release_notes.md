| [Home](./README.md) |
|----------------------|

# What's New

| Compatible Version | FortiSOAR v7.4.1 and later |
|--------------------|----------------------------|

| NOTE | If you have updated any of the System View Templates(SVTs), Module Metadata (MMD), and playbooks, ensure to take a backup before updating SOAR Framework solution pack, as any changes that you have made will be overwritten. |
|------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

## New Feature

- Introduced a new **Extract Indicators - Create File Indicator** playbook in the *03 - Enrich* collection, the playbook creates file indicators extracted from suspicious email attachments and follow the nomenclature for the file indicator value as `File - <FileName> - <FileHash-MD5>`

- The **Extract Indicators** playbook in the *03 - Enrich* collection now provides a facility to exclude files from file indicator creation.

    >**Note:** A new global variable `Excludelist_Files` has been introduced for the same. the file names or extensions mentioned in this global variable will be excluded from the file indicator creation. By default, this global variable will be shipped empty.

## Playbook Enhancements

- The **Find and Relate Similar Alerts** playbook in the *03 - Triage* collection now finds alerts for the last 30 days and in MSSP env it finds alerts belonging to the same tenant the playbook executing on.

- The **Flag Indicators Linked Across Multiple Alerts** playbook in the *03 - Triage* collection now flags to only those alerts that were generated in the last 30 days.

## Module Enhancements

### Alerts
- Introduced a new `Ticket ID` field which will only be visible when the field value is not null.

### Assets
- Introduced a new `BES Cyber Asset Category` field and a new picklist with same name which will only be visible when the field value is not set.

- Rearranged the Asset List View Columns. The sequence of Asset fields in the list view is as follows:
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
- Added `Technique ID` field to the detailed view of Incident which will only be visible when the field value is not null.
- Introduced a new `Ticket ID` field which will only be visible when the field value is not null.

### Indicators
- `TLP`, `Expired`, and `Expired On` fields in the indicator module have been marked by default replicable from the tenant node in the MSSP environment.

### Key Store
- Introduced new fields named `JSON Value` and `Notes`

### SLA Templates
- Updated field type from `picklist` to `multipicklist` for the *Pause Incident SLA On* and *Pause Alert SLA On* fields to enable setting multiple "Pause SLA On" statuses.
- Also updated Detailed View of the SLA Templates module accordingly.

## Dashboard Enhancements

### Analyst Dashboard
-  In the `Analyst` dashboard's Critical Alerts Tab, updated the display condition to show only high and critical severity alerts.

## Rules Enhancements
### Notify On Pending Internal Manual Input Rule
- The new rule has been introduced to send email notifications to FortiSOAR users when the option to customize the email body is selected during the creation of manual input for internal users.