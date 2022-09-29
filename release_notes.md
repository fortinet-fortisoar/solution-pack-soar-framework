# What's New

## Playbook Enhancements

- The playbook **Extract Indicators**, from the collection **03 - Enrich**, has been improved so that, if the linked alert has the same indicator as the indicator being enriched, it links the indicator to the alert and updates the indicator's `Last Seen` field.
- The *Wait* step is now conditional ensuring that the playbook waits only until the new and current indicators are enhanced, not for a set amount of time.
  - Also, if a playbook's *Wait* condition is not met within the allocated time, new sequence of events can be triggered.

- Connector-specific indicator enrichment playbooks can now be referenced from other playbooks. You can run these *pluggable* playbooks as-is or tweak them to suit your requirements. These *pluggable* playbooks make generic enrichment playbooks redundant and help create a more optimized flow for SOAR Framework.
    - To achieve these objectives, the entire playbook collection **03 - Enrich(pluggable)** and following playbooks from **03 - Enrich** collection, are no longer used by SOAR Framework solution pack 2.0.0.
      - Indicator (Type All) - Get Latest Reputation
      - Indicator (Type Domain) - Get Reputation
      - Indicator (Type Email) - Get Reputation
      - Indicator (Type File - MD5) - Get Reputation
      - Indicator (Type File) - Get Reputation
      - Indicator (Type Host) - Get Reputation
      - Indicator (Type IP) - Get Reputation
      - Indicator (Type Port) - Get Reputation
      - Indicator (Type Process) - Get Reputation
      - Indicator (Type URL) - Get Reputation
      - Indicator (Type User Account) - Get Details
      - Indicator (Type File) - Get Reputation (Fortinet Sandbox)
      - Indicator (Type URL) - Get Reputation (Fortinet Sandbox)
      - Fortinet FortiSandbox (Get Reputation) - Get Scan Results

    - Following new optimized playbooks are now part of SOAR Framework 2.0.0
      - Enrich Indicators (Type All)
      - Enrich Indicator (Type IP)
      - Update/Initialize Indicator Enrichment Global Variables
      - Retrieve Configured Enrichment Connectors
      - Delete Enrichment Global Variables

    - The Following connectors, with stated versions, have specific *pluggable* playbooks that you can reference:
      | Connector                               | Version |
      |:----------------------------------------|:-------:|
      | APIVoid                                 |  1.0.1  |
      | Active Directory                        |  2.2.1  |
      | Anomali ThreatStream                    |  2.3.0  |
      | Fortinet FortiGuard Threat Intelligence |  3.0.2  |
      | Fortinet FortiSandbox                   |  1.0.4  |
      | Fortinet Web Filter Lookup              |  1.0.1  |
      | IBM XForce                              |  1.0.2  |
      | IP Quality Score                        |  1.0.1  |
      | IP Stack                                |  1.0.1  |
      | Symantec DeepSight Intelligence         |  1.0.2  |
      | URLScan.io                              |  1.1.1  |
      | VirusTotal                              |  3.0.2  |
      | Whois RDAP                              |  1.0.2  |

      The enrichment Playbooks included with these connectors are detailed in respective [connector docs](https://docs.fortinet.com/fortisoar/connectors).

      To understand how pluggable enrichment works refer to [Using the "Pluggable" Indicator Enrichment](./docs/extending-default-indicator-enrichment-process.md#using-the-pluggable-indicator-enrichment) section

      >**NOTE**: For help and initial actions required to upgrade to SOAR Framework Solution Pack version 2.0.0, please refer to [Upgrading to FortiSOAR v2.0.0](./docs/moving-to-sfsp-2-0-0.md).


## Module Enhancements
- A new field **Was Personal Data Affected?**, in the **Incidents** module, now captures if personal data was affected.
- The field **MITRE ATT&CK ID** has now been renamed to **Technique ID** to be inline with the MITRE conventions. This change reflects in both *Alerts* and *Incidents* modules.
    - The **MITRE Technique** field in *Alerts* module has now been renamed to **Technique**.
- *Open* and *Re-opened* are now available as options under the *Status* drop-down of the **Tasks** module.
- *Critical* and *Very Critical* are now available as options, under the *Asset Criticality* drop-down of the **Assets** module, instead of *Super High* and *Super Duper High*.
    - This information has been updated in the *Is Asset Critical* step of the **Prioritize Alerts With VIP Assets** playbook under the **03 - Triage** collection.
- **ImpactROI** field now appears under the Incident module to support SOC Management widget for Return on Investment (ROI) calculations.

## Resolved Issues

The following is a list of some of the important defects addressed in the **SOAR Framework v2.0.0**.

- **Bug #0839718**: Whitelisted IP addresses, domains, and URLs are now excluded while extracting the indicators from the alert  
- **Bug #0831070** - The **Action - Host - Isolate Host** playbook under the collection **04 - Actions** was failing due to a missing trigger condition. The conditional statement has been added and the playbook no longer fails.
