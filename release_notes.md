# What's New

>**Compatible Version**: FortiSOAR v7.2.1 and later

## Playbook Enhancements

- Following playbooks have been added under the **03 – Enrich** collection to enrich the Registry, Process, Port, and Host indicator type
  - Indicator (Type Registry) - Get Reputation
  - Indicator (Type Process) - Get Reputation
  - Indicator (Type Port) - Get Reputation
  - Indicator (Type Host) - Get Reputation

## Module Enhancements
- `threatIntelFeeds` field is now available under the **Indicator** module detail view. After the installation of **Threat Intel Management** Solution Pack, this field shows the relationship between threat intel feeds and the indicator.

## Resolved Issues

The following is a list of some of the important defects addressed in the **SOAR Framework v2.0.1**.

- **Bug# 0848269**: Handled the race conditions for the following playbooks under the collection **06 - IRP - Case Management**.   
  - Alert - [02] Capture Ack SLA (Upon Update)
  - Incident - [02] Capture Ack SLA (Upon Update)
  - Alert - [03] Capture Response SLA (Upon Update)
  - Incident - [03] Capture Response SLA (Upon Update)
  - Alert - [05] Update Response and Ack Due date (Post Severity Change)
  - Incident - [05] Update Response and Ack Due date (Post Severity Change)
- **Bug# 0849828** - The **Extract Indicators** playbook under the collection **03 - Enrich** has been modified as follows:
  - Removed the *Wait* condition *indicator enrichment status is not completed*
  - A new condition *indicator enrichment status is completed* avoids the re-enrichment of indicators.
