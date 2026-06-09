| [Home](../README.md) |
|----------------------|

<!-- - Overview only
- UI walkthrough
- Field reference
- Alert-to-identity lifecycle
- Integration behavior
- Investigation workflow
- Admin configuration
- Playbook examples -->

# Identities Module

The Identities module provides a centralized repository for identity-related information ingested from FortiAnalyzer and FortiSIEM. The module is designed to support identity correlation, enrichment, and investigation workflows within FortiSOAR.

Identity records can be associated with alerts, cases, assets, and related entities to provide additional investigation context. The module acts as a normalization and correlation layer for user-related information extracted from ingested data.

The Identities module is currently foundational in scope and is intended to be extended through organization-specific playbooks and integrations.

You can implement custom playbooks to extract user information from alerts and create or update identity records as required.

## Identity Lifecycle in FortiSOAR

A typical identity workflow in FortiSOAR consists of the following stages:

1. An alert is ingested from FortiAnalyzer or FortiSIEM.
2. User-related information is extracted from the alert.
3. A custom playbook creates or updates an identity record.
4. Risk score is synchronized from the source platform.
5. The identity record is correlated with related alerts, cases, or assets.

>[!NOTE]
>
>The Identities module currently does not enforce a predefined ingestion or synchronization workflow. Identity lifecycle behavior depends on the playbooks and integrations implemented by the organization.
>

## Creating an Identity Record

Identity records can be created manually from the Identities module. Automated identity creation workflows can be implemented through custom playbooks.

Click **Resources** <picture><source media="(prefers-color-scheme: dark)" srcset="./res/icon-resources-light.svg"><source media="(prefers-color-scheme: light)" srcset="./res/icon-resources-dark.svg"><img alt="" src="./res/icon-resources-dark.svg"></picture> > **Identities** <picture><source media="(prefers-color-scheme: dark)" srcset="./res/icon-identities-light.svg"><source media="(prefers-color-scheme: light)" srcset="./res/icon-identities-dark.svg"><img alt="" src="./res/icon-identities-dark.svg"></picture> in the left-navigation to open the **Identities** module in the list view.

The following fields are available when creating an identity record:

| Field      | Description                                                                                                         |
| ---------- | ------------------------------------------------------------------------------------------------------------------- |
| Title      | Job title or designation associated with the identity.                                                              |
| User Name  | Username associated with the identity.                                                                              |
| User ID![mandatory](./res/icon-asterisk.svg)    | Unique identifier for the identity record. Used as the primary key for mapping and deduplication.                   |
| First Name | First name associated with the identity.                                                                            |
| Last Name  | Last name associated with the identity.                                                                             |
| First Seen | Timestamp indicating when the identity was first observed. Automatically updated from ingested telemetry.           |
| Last Seen  | Timestamp indicating the most recent observation of the identity. Automatically updated from ingested telemetry.    |
| Risk Score | Numeric risk score associated with the identity. Risk scores are sourced from FortiAnalyzer or FortiSIEM telemetry. |

## Identity Fields Reference

| Field                   | Description                                                                    |
| ----------------------- | ------------------------------------------------------------------------------ |
| User ID                 | Unique identifier for the identity record. Used for mapping and deduplication. |
| User Name               | Username associated with the identity.                                         |
| Risk Score              | Numeric risk score received from FortiAnalyzer or FortiSIEM telemetry.         |
| Identity Risk           | Risk classification derived from ingested risk telemetry.                      |
| Importance              | Importance value received from FortiAnalyzer telemetry.                        |
| VPN IP                  | Last known VPN IP associated with the identity.                                |
| Source Data             | Network or source context received from FortiAnalyzer or FortiSIEM telemetry.  |
| FortiAnalyzer Source ID | Event source identifier associated with FortiAnalyzer telemetry.               |
| FortiSIEM Source ID     | Event source identifier associated with FortiSIEM telemetry.                   |
| User Group              | Group-related information associated with the identity record.                 |
| First Seen              | Timestamp indicating when the identity was first observed.                     |
| Last Seen               | Timestamp indicating the most recent observation of the identity.              |

## Identity Correlations

Identity records can be correlated with the following entities within FortiSOAR:

- Alerts
- Cases
- Assets

Identity relationships can be viewed from the **Correlations** > **Identities** tab within supported modules and records.

These relationships provide additional investigation context and help analysts pivot between related entities during investigations.

## Detailed View

The identity details page is divided into multiple fixed sections that organize identity-related information.

### Identity Summary and Risk

Displays core identity information and risk-related telemetry, including:

- User Name
- First Name
- Last Name
- User ID
- Importance
- Risk Score
- Identity Risk

### Location and Network Context

Displays network-related context associated with the identity, including:

- Location
- Source Data
- VPN IP

Location information may be derived from VPN or IP telemetry received from integrated platforms.

### Organizational Context

Displays organization-related identity information, including:

- Title
- Department
- Manager
- FortiAnalyzer Source ID
- FortiSIEM Source ID

### Security Details

Displays additional security-related identity information, including:

- First Seen
- Last Seen
- User Group

## Extending Identity Workflows

Organizations can extend the Identities module using custom playbooks and integrations.

Custom workflows can be implemented to:

- Create identity records from ingested alerts
- Update risk-related telemetry
- Enrich identity records with external data
- Synchronize identity information from external sources
- Implement organization-specific scoring or automation logic

Workflow behavior depends on the integrations, telemetry sources, and playbook logic implemented by the organization.

LDAP and Active Directory synchronization capabilities are planned but are not currently production-ready.

## Limitations and Current Scope

The current implementation of the Identities module is foundational and intended to support future extensibility.

Current limitations include:

- No out-of-the-box automatic identity ingestion
- No production-ready LDAP or Active Directory synchronization
- No predefined dashboards
- No predefined identity automation workflows

Identity lifecycle behavior, enrichment, synchronization, and automation depend on organization-specific playbooks and integrations.


## Next Steps

| [Installation](./setup.md#installation) | [Configuration](./setup.md#configuration) | [Usage](./usage.md) | [Contents](./contents.md) |
|-----------------------------------------|-------------------------------------------|---------------------|---------------------------|
