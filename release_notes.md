# What's New

>[!Note]
>*Compatible Version*: FortiSOAR v8.0.0 and later

## Enhancements

### Renaming of Incident to Case

*Incident* has been renamed to **Case**. Now, alerts will be escalated as **Case** instead of as *Incidents*.

### Identities Module

A new **Identities** module has been created to act as a correlation layer for user-related information extracted from ingested data. A new tab *Identities* now appears on the details page of modules such as Alert or a *Case*, under the **Correlations** tab.

### AI Integration

An **AI Investigation** tab in an alert's details page launches an investigation, analyzes alerts, and summarizes evidence to help reach a verdict faster.

## Playbook Enhancements

- Updated the playbook **Enrich Indicators (Type All)** to enrich indicators of type `host`

- Updated the playbook **Indicator (Type Host) - Get Reputation** to search for an existing asset in TIPs like ServiceNow and add the asset details in the host's record

- Added the following playbooks in the collection **05 - Hunts** as part of the *Pluggable* hunt implementation

  - Hunt (On Create) - Initiate IOC Hunt

  - Hunt Indicators (Type All)

  - Reset Hunt Global Variables

  - Indicator (Manual Trigger) - Initiate IOC Hunt

## Miscellaneous

- Added new dashboards &ndash; `System Health & Workflow Insights` and `System Overview`

- New Color Code added for the picklists &ndash; *Alert Status* and *Incident Status*.

- Roles and navigation changes have been decentralized to optimize performance. **SOAR Essentials** solution pack now manages roles and navigation for SOAR Framework.

- Color codes associated with picklists have been standardized across the user interface.

- Alerts and Cases list view now includes summaries of alerts and cases in various stages of investigation.

- Updated the **SLA Countdown** widget configuration to support the new title setting, allowing the paused SLA title to appear in both alerts and the case detail view.

### Bug Fixes

- Updated the connector name from *CarbonBlack Response* to **VMware Carbon Black EDR** in SOAR Framework solution pack playbooks.

- The manual input step has indicator IRI mapped to parameter and input record &ndash; whichever is available. Earlier, in the following playbooks, the manual input step required both the input record and input record IRI parameters to be mapped:

    - Action - Host - Block (Indicator)
    - Action - Host - Unblock (Indicator)
    - Action - Host - Isolate Host Action - URL - Unblock (Indicator)
    - Action - URL - Block (Indicator)
    - Action - Domain - Block (Indicator)
    - Action - Domain - Unblock (Indicator)
    - Action - IP Address - Unblock (Indicator)
    - Action - IP Address - Block (Indicator)
    - Action - IP Address - Block (FortiGate,FortiEDR)
    - Action - File MD5- Unblock (Indicator)
    - Action - File MD5 - Block (Indicator)
    - Action - File - Unblock (Indicator)
    - Action - File - Block (Indicator)
    - Action - Email Address - Unblock (Indicator)
    - Action - Email Address - Block (Indicator)
