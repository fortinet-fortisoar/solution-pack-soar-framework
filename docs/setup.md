| [Home](../README.md) |
|----------------------|

# Installation

**SOAR Framework** Solution Pack installs with Fortinet's FortiSOAR and hence does not require any prerequisites or separate installation instructions.

## Prerequisites

The **SOAR Framework Solution Pack** solution pack installs the following solution pack &ndash; if not already installed.

| Solution Pack Name | Version          | Purpose                                                      |
|:-------------------|:-----------------|:-------------------------------------------------------------|
| Platform Utilities | v1.0.0 and later | Required for indicator extraction using the Key Store module |

# Configuration

**SOAR Framework Solution Pack** comes with a host of connectors listed [here](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/develop/docs/contents.md#connector-list). There are multiple other connectors with which this solution pack can integrate.

To configure any connector, refer to [Configuring a connector](https://docs.fortinet.com/document/fortisoar/0.0.0/configuring-a-connector/1/configuring-a-connector).

For detailed instructions on how to configure *each* connector refer to [FortiSOAR Connectors](https://docs.fortinet.com/fortisoar/connectors).

## Highly Recommended Solution Packs

The following is a list of solution packs that come highly recommended as they target some of the most complex and common use cases:

- **Threat Intelligence Management (TIM)**: Enables ingestion, aggregation and normalization of threat-intel feeds, threat actors, IOCs, reports; facilitates correlation of threat data into alerts/incidents.

- **Outbreak Response Framework**: Used to investigate outbreak alerts (e.g. widespread malware, zero-day exploits, mass-exploitation campaigns) — helps SOC teams respond to large-scale outbreaks, enrich IOCs, perform threat hunting, and coordinate remediation.

- **Vulnerability Management**: Allows integration of vulnerability scanner outputs and helps correlate CVEs with threat intel and assets — enabling risk-based asset & vulnerability management and proactive remediation.

- **Continuous Delivery**: Helps manage FortiSOAR content (playbooks, connectors, modules) via source-control; supports change management, versioning, and safer deployments — especially useful in environments with multiple administrators or frequent updates.

- **MITRE ATT&CK Enrichment Framework**: Integrates the MITRE ATT&CK knowledge base with FortiSOAR — enabling mapping of alerts/incidents to ATT&CK tactics/techniques, supporting threat-hunting, enrichment, and structured adversary behavior modeling.

- **Phishing Email Response**: Provides playbooks and workflows to investigate suspicious emails (e.g. .eml/.msg or forwarded mails), extract IOCs (URLs, attachments, senders), analyze sender reputation/spoofing, and escalate — useful if phishing is a common threat vector.

- **Brute Force Attack Response**: Automates detection and response to login-failure / brute-force attacks: triggers playbooks based on log/SIEM inputs, extracts key indicators (e.g. source/destination IPs, user accounts), enriches them and supports containment actions.

- **C2 Malware Traffic Response**: Designed for detecting and responding to command-and-control (C2) or suspicious outbound network traffic — includes playbooks for network-activity investigation, IP/domain reputation enrichment, and automated containment or blocking actions.

- **Lateral Movement & VPN Breach Response**: Helps in investigating and responding to lateral-movement or VPN-breach events — useful when there are indications of internal compromise or unauthorized remote access.

- **Impossible Traveler Threat Response**: Helps to respond to concurrent successful authentications to the same account from multiple countries.                                                                                                                                             |
# Next Steps

| [Usage](./usage.md) | [Contents](./contents.md) |
|---------------------|---------------------------|
