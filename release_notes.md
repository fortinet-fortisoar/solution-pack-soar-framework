# What's New

>**Compatible Version**: FortiSOAR v7.2.2 and later

## Playbook Enhancements

- Modified `Generate War Room Report` playbook under the collection `06 - IRP - War Room`
    - The loading icon will now visible for the `Generate Report` button till the report is generated for the war room record
- Removed `Link Similar Emails` playbook under the collection `06 - IRP - Case Management` 

## Module Enhancements

- **Asset Module**
    - Added new `Source Data` field
    - Renamed `Related Record` tab to `Correlations` in Asset detailed view

- **Alert Module**
    - Added the `Event` module in the `Correlations` tab of the Alert detailed view
    - Added the tooltips for fields `IP Addresses` and `File Hashes`

- **Indicator Module*
    - A new `Failed` picklist item is added to the *Enrichment Status* picklist

## Resolved Issues

- Fixed the `Fetch and Link Team to Related Records` playbook under `08 Utilities` collection which was failing when "IP Addresses" and "File Hashes" fields are populated in the alert record 