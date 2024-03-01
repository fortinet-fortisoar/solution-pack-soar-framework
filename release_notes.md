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
        <td>Before updating the SOAR Framework solution pack, make sure to back up any modifications you have made to <strong>System View Templates (SVTs)</strong>, <strong>Module Metadata (MMD)</strong>, and <strong>Playbooks</strong>. This is essential because updating the solution pack overwrites any changes you might have made.</td>
    </tr>
</table>

## Module Enhancements

### Alerts

- Under `Type Details` section in the Alert Detailed View (SVT), all the empty fields will be hidden by default

### Indicators

- For the `File` type indicator now the `File` field is mandatory 
> **Note:** Above change will reflect in fresh install. But for upgrade it is recommended to do this change manually using Application Editor in Settings
- Added `Tenant` field in module's *Record Uniqueness* settings

### War Rooms
- The war room module is marked as `Team Ownable` and `User Ownable` by default

### i18n changes
- Added *English* and *French* language support to all the modules comes OOB with SFSP
> **Note:** This change applicable only FortiSOAR 7.5.0 and later

## Playbook Enhancements

- "Extract Indicators" playbook in the *03 - Enrich* playbooks collection 
    - This playbook now appends the indicators to the Alert record instead of overwriting 
    - This playbooks now links Alert's teams to the extracted Indicators from an Alert to ensure visibility of extracted Indicators to the owners of the alert
- Updated below playbooks in the *06 - IRP - Case Management* collection now calculates Pause SLA time using the `SLA Calculator` connector.
    - *Alert - [02] Capture Ack SLA (Upon Update)*
    - *Alert - [03] Capture Response SLA (Upon Update)*
    - *Incident - [02] Capture Ack SLA (Upon Update)*
    - *Incident - [03] Capture Response SLA (Upon Update)*

- Updated below playbooks in the *06 - IRP - Case Management* collection, in shared tenancy environment if SLA templates for the tenant is not present then the SLA playbooks fallbacks to default SLA Template
    - *Fetch SLA Details*
    - *Alerts - Update SLA Details*
    - *Incidents - Update SLA Details*

- Introduced new playbooks in the *08 - Utilities* collection:
    - *Manage Closed Alerts -* Manually triggered playbook that identifies closed alerts from the past seven days.
    - *Alert - Record Closure Validation -* Post alert closure this playbook ensures alerts cannot be closed if tasks or manual inputs are incomplete, prompting user confirmation for reopening or closure.
    - *Incident - Record Closure Validation -* Post Incident closure this playbook ensures incidents cannot be closed if tasks or manual inputs are incomplete, prompting user confirmation for reopening or closure.