# Upgrade SOAR Framework from v1.x.x to v2.0.1

To make the most of the SOAR Framework v2.0.1, you must perform the following steps before initiating an upgrade to SOAR Framework Solution Pack v2.0.1.

1. Navigate to **Automation** > **Playbooks** > **03 - Enrich**.
2. Search for and deactivate following playbooks:
    1. Indicator (Type All) - Get Latest Reputation
    2. Indicator (Type Domain) - Get Reputation
    3. Indicator (Type Email) - Get Reputation
    4. Indicator (Type File - MD5) - Get Reputation
    5. Indicator (Type File) - Get Reputation
    6. Indicator (Type IP) - Get Reputation
    7. Indicator (Type URL) - Get Reputation
    8. Indicator (Type User Account) - Get Details
    9. Indicator (Type File) - Get Reputation (Fortinet Sandbox)
    10. Indicator (Type URL) - Get Reputation (Fortinet Sandbox)
    11. Fortinet FortiSandbox (Get Reputation) - Get Scan Results
3. Update the following connectors to the mentioned version. This action lays the groundwork for using the *pluggable* playbooks included with these connectors.

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

Now your FortiSOAR system is ready for an upgrade to SOAR Framework v2.0.1.

>**NOTE**: After updating the connectors to the stated version if the enrichment summary is not available on an indicator, you may have to:
> 1. Execute **Delete Enrichment Global Variables** playbook from **03 – Enrich** collection to delete the following global variables:
>     - `URL_Enrichment_Playbooks_IRIs`
>     - `File_Enrichment_Playbooks_IRIs`
>     - `IP_Enrichment_Playbooks_IRIs`
>     - `Domain_Enrichment_Playbooks_IRIs`
>     - `FileHash_Enrichment_Playbooks_IRIs`
>     - `User_Enrichment_Playbooks_IRIs`
>     - `Email_Enrichment_Playbooks_IRIs`
> 2. Force the sync with FortiSOAR Content Hub servers. Execute the following commands on the FortiSOAR command line interface (CLI) to re-sync.
>     ```bash
>     sudo -u nginx php /opt/cyops-api/bin/console fortisoar:contenthub:sync -fs
>     ```
