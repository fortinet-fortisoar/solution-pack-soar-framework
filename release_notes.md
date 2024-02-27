| [Home](./README.md) |
|---------------------|

# What's New

<table>
    <tr>
        <th>Compatible Version</th>
        <td>FortiSOAR v7.4.1 and later</td>
    </tr>
</table>

<table>
    <tr>
        <th>NOTE</th>
        <td>Before updating the SOAR Framework solution pack, make sure to back up any modifications you have made to <strong>System View Templates (SVTs)</strong>, <strong>Module Metadata (MMD)</strong>, and <strong>playbooks</strong>. This is essential because updating the solution pack overwrites any changes you might have made.</td>
    </tr>
</table>

## Module Enhancements

### Alerts

- Marked the `Hide Empty Fields` checkbox is by default set as `true` in Alert Detailed View

### Indicators

- Marked the `File` field of the indicator module mandatory for the `File` type indicator
> **Note:** This change won't show up in SFSP upgrades. It's best to apply it manually to prevent the incorrect creation of file indicators.
- Added `Tenant` field of indicator module in *Record Uniqueness* settings

### War Rooms
- The war room module is marked as `Team Ownable` and `User Ownable`

### i18n changes
- Added *English* and *French* language support to all the modules comes OOB with SFSP
> **Note:** This change will only show up in FortiSOAR 7.5.0 onwards

## Playbook Enhancements

- Updated the "Extract Indicators" playbook in the *03 - Enrich* playbooks collection 
    - This playbook now appends the indicators to the alert record instead of overwriting 
    - This playbooks now links Alert's teams to the extracted Indicators from alert to ensure visibility of extracted indicators to the owners of the alert

- Updated below playbooks in the *06 - IRP - Case Management* collection now accurately calculate Pause SLA time using the `SLA Calculator` connector.
    - *Alert - [02] Capture Ack SLA (Upon Update)*
    - *Alert - [03] Capture Response SLA (Upon Update)*
    - *Incident - [02] Capture Ack SLA (Upon Update)*
    - *Incident - [03] Capture Response SLA (Upon Update)*

- Updated below playbooks in the *06 - IRP - Case Management* collection, the playbooks now determine that in shared tenancy environment if SLA templates for the tenant is missing then the playbooks fallbacks to default SLA Template and update the SLA Details accordingly
    - *Fetch SLA Details*
    - *Alerts - Update SLA Details*
    - *Incidents - Update SLA Details*

- Introduced new playbooks in the *08 - Utilities* collection:
    - *Manage Closed Alerts -* Identifies closed alerts from the past seven days.
    - *Manage Closed Alerts - Remove Pending Manual Inputs -* Retrieves associated pending manual inputs and deletes them.
    - *Alert - Record Closure Validation -* Ensures alerts cannot be closed if tasks or manual inputs are incomplete, prompting user confirmation for reopening or closure.
    - *Incident - Record Closure Validation -* Ensures incidents cannot be closed if tasks or manual inputs are incomplete, prompting user confirmation for reopening or closure.