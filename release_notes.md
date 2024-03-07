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

- Under **_Type Details_** section in the Alert Detailed View template (SVT), empty fields are hidden by default.

### Indicators

- The field `Tenant` has now been added to the module's *Record Uniqueness* settings.

### War Rooms

- The war room module is marked as `Team Ownable` and `User Ownable`, by default

### Language Support

- Added support for following languages, in all modules, out-of-the-box:
    - English
    - Chinese (Simplified)
    - Japanese
    - Korean

> **Note:** This change is applicable from FortiSOAR 7.5.0 and later.

## Playbook Enhancements

- Following changes have been made to the playbook **Extract Indicators** in the collection *03 - Enrich*:
    - Appends the indicators to the alert record instead of overwriting
    - Links an alert's teams to the indicators extracted from an alert. This linking ensures that the extracted indicators are visible to the owners of the alert.

- Following playbooks in the collection *06 - IRP - Case Management* now calculate **_Pause SLA_** time using the **SLA Calculator** connector:
    - Alert - [02] Capture Ack SLA (Upon Update)
    - Alert - [03] Capture Response SLA (Upon Update)
    - Incident - [02] Capture Ack SLA (Upon Update)
    - Incident - [03] Capture Response SLA (Upon Update)

- Following playbooks in the collection *06 - IRP - Case Management* fallback to the default SLA template, in a shared tenancy environment, if SLA templates for the tenant are not present:
    - *Fetch SLA Details*
    - *Alerts - Update SLA Details*
    - *Incidents - Update SLA Details*

- Following new playbooks have been added to the collection *08 - Utilities*:
    - **Manage Closed Alerts**: A manually triggered playbook that identifies alerts closed in the last seven days.
    - **Alert - Record Closure Validation**: Stops an alert's closure until associated tasks and manual inputs are complete. It prompts the user to reopen or close the associated task or manual input before they close the alert.
    - **Incident - Record Closure Validation**: Stops an incident's closure until associated tasks and manual inputs are complete. It prompts the user to reopen or close the associated task or manual input before they close the incident.