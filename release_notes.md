# What's New

<table>
    <tr>
        <th>Compatible Version</th>
        <td>FortiSOAR v7.6.0 and later</td>
    </tr>
</table>

<table>
    <tr>
        <th>NOTE</th>
        <td>Before updating the SOAR Framework solution pack, make sure to back up any modifications you have made to <strong>System View Templates (SVTs)</strong>, <strong>Module Metadata (MMD)</strong>, and <strong>Playbooks</strong>. This is essential because updating the solution pack overwrites any changes you might have made.</td>
    </tr>
</table>

## Indicator Extraction

- A new playbook **Extract Indicators (Incidents)** now helps extract indicators from independently created new incidents.

    <table>
        <tr>
            <th>NOTE</th>
            <td>Indicators are extracted only from independently created new incidents, not from escalated incidents.</td>
        </tr>
    </table>

- A **Indicator Extraction Configuration** widget now accepts indicators to be excluded from extraction and populates the corresponding key store records

    - Key store records replace existing global variables for indicator extraction as per the following table:

        | Global Variable Name             | Key Store Record               |
        |:---------------------------------|:-------------------------------|
        | No corresponding global variable | `sfsp-excludelist-cidr-ranges` |
        | `Excludelist_IPs`                | `sfsp-excludelist-ips`         |
        | `Excludelist_URLs`               | `sfsp-excludelist-urls`        |
        | `Excludelist_Domains`            | `sfsp-excludelist-domains`     |
        | `Excludelist_Files`              | `sfsp-excludelist-files`       |
        | `Excludelist_Ports`              | `sfsp-excludelist-ports`       |

- Renamed the playbook **Extract Indicators** to **_Extract Indicators (Alerts)_**

- Added following fields to the **Incident** module

    - **Escalated** is a picklist with `Yes` and `No` as options
    - **State** is a picklist with `AlertState` values as its options

    These fields help extract indicators from newly-created incidents

- The following playbooks changes have been introduced to extract indicators from incidents:
    - Created a new playbook **Extract Indicators (Incidents)** 
    - Renamed the playbook *Extract Indicators* to **Extract Indicators (Alerts)**

- Incident fields in the global variable `Indicator_Type_Map` have been mapped as follows for indicator extraction from an incident:

    ```JSON
    "dLLName": "Process",
    "filehash": "FileHash-MD5",
    "processName": "Process",
    "destinationIP": "IP Address",
    "sourceIP": "IP Address",
    "recipientEmailAddress": "Email Address",
    "targetAsset": "Host",
    "senderDomain": "Domain",
    "senderEmailAddress": "Email Address"
    ```

- A new **Custom Picklist** widget helps generate customized messages for change in a pre-selected picklist

## SOAR Framework Optimization

- A new setup guide wizard launches automatically on first login. It contains a list of tasks whose completion is recommended as part of first time setup.

- **Key Store** module has been removed from *SOAR Framework* and is now a part of **Platform Utilities** solution pack

    - The playbook **04 - Actions > Add to Exclude List** now updates the Key Store records instead of global variables

- The **Hunt** module has been removed from *SOAR Framework* and is now a part of **Threat Intel Management** solution pack.

- **SLA Templates** module has been removed from *SOAR Framework* and is now a part of **SLA Management** solution pack

    - The following playbooks have been moved to the **SLA Management** solution pack:
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

- The following playbooks have been moved to the **SOC Utilities** solution pack:

    - 06 - IRP - Reporting > Export Selected Records
    - 06 - IRP - Reporting > Import Data
    - 08 - Utilities > Activate Inactive Users
    - 08 - Utilities > Activate Inactive Users - Update User Status
    - 08 - Utilities > Convert FortiSOAR User to SAML - Collect User Email IDs
    - 08 - Utilities > Convert FortiSOAR User to SAML - Update User Type

- Removed the following playbooks from the collection **06 - IRP - Case Management** as the **Approval** module is no longer a part of SOAR Framework solution pack:

    - Approval - On Email Receipt - Process Email
    - Approval - On Email Receipt (IMAP)
    - Approval - On Email Receipt (Exchange)
    - Approval - On Create

- **Code Snippet** connector now no longer installs with the SOAR Framework solution pack. It is still available to install from the Content Hub.

- A new notification rule replaces the playbook **Notify Failed Playbook Executions**.

- The following playbooks are now inactive by default:

    - Compute Alert Priority Weight(Post Update)
    - Compute Alert Priority Weight(Post Update - Indicator Linked)
    - Compute Alert Priority Weight(Post Update - Indicator Reputation Update)

<table>
    <th>NOTE</th>
    <td>To compute priority weight of an alert, mark these playbooks as <strong>Active</strong> from <strong>Automation</strong> <img src="./docs/res/icon-chevron-right.svg"> <strong>Playbooks</strong> <img src="./docs/res/icon-chevron-right.svg"> <strong>03 - Triage</strong>.</td>
</table>

## Incident Detailed View

- The *Picklist as Phases* widget is now a part of an incident's detail view to show incident progress as steps

## Playbook Enhancements

- Updated the *04 - Actions > Asset - Deploy Patch* playbook's approval step as per the new flow

- Users can now choose to close the alert after selecting the reason on the manual input requested by the playbook *Escalate to incident*.

## Bug Fixes

- Fixed an issue where the *Extract Indicator* playbook failed to execute for alerts of type *Suspicious Email* and *Phishing*, if the attached file did not have any content.

- A pre-processing rule now ensures that indicators of type file are created only when a file is attached to the indicator

- Fixed response mappings in the *04 - Action > Action - Asset Mitigation* playbook's manual input step

- Escalate Playbook button now becomes invisible when an alert is escalated.