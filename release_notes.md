# What's New

<table>
    <tr>
        <th>Compatible Version</th>
        <td>FortiSOAR v7.6.4 and later</td>
    </tr>
</table>

### MSSP Playbook Execution Flexibility

- The *On Create*, *On Update*, and *On Delete* playbooks now offer more control in MSSP environments.

    Instead of running solely on the instance where a record is created, administrators can now choose to execute these playbooks on the master node, the tenant node, or both.

- Optimized *Created* and *Replicated* node executions (introduced in v7.4.2) to prevent execution conflicts.

- Resolved issues where the enrichment playbooks failed to run on either node in certain MSSP scenarios.

This update gives MSSPs more operational consistency and simplifies cross-node automation strategies.

### Expanded Indicator & File Content Extraction

- Private IP addresses are now being successfully extracted from attachments, ensuring better visibility across diverse data sources.

- The file content extraction engine has been upgraded to identify indicators even in previously unreadable formats&mdash;including **`.so`** and **`.docx`** files&mdash;improving the breadth and reliability of automated artifact analysis.

### SVT Module Performance Improvements

The SVT Module's views have been optimized to deliver faster load times and smoother interaction, especially in high-volume environments. The following cover some enhancements that have been made:

- Removed the **Execute Playbooks** widget from SVTs and from the *Detailed View* of the following modules:

    - Alerts  
    - Assets  
    - Incidents  
    - Events  

- Modules that do not contain *required* fields, or *default Add Views* ('add a new record' form), no longer show an Add View in SVT.

- Added the missing **Add View** for the **Campaign** module.


### Playbook Enhancements

- **03 - Triage > Map Historical Alerts and Escalate for Malicious Indicators**
  Now properly creates an incident when multiple alerts are tied to the same indicator. Newly created alerts linked to that indicator are automatically associated with the same incident, streamlining case grouping and escalation logic.

- **03 - Triage > Flag Indicators Linked Across Multiple Alerts**
  Now automatically adds comments or flags to relevant alerts when malicious indicators appear across multiple alert records, helping analysts quickly understand cross-alert relationships

- **Incident Creation for Multiple Linked Alerts** has now been enhanced to create incidents based on linked historical alerts. The playbook now:

    - Maps historical alerts

    - Escalates alerts to incidents when malicious indicators are detected

    - Updates existing incidents or creates new ones as required

## Fixes

- Resolved issues where some playbooks failed after the *Code Snippet* connector began operating in safe mode by default.

    The following playbooks' steps utilizing the Code Snippet connector steps have been replaced with steps **Jinja** or **Utilities connector** logic.

    - *06 - IRP - Reporting > Export as CSV*
    - *06 - IRP - Reporting > Get Paginated Records*
    - *06 - IRP - Case Management > Ingest IOC from CSV File*

- Earlier, expired indicators were incorrectly marked as *not expired* by the playbook **Indicator - Check Expiry Status** under the collection *06 - IRP - Case Management*.

    Expired indicators now correctly show indicators' expiration status.

- Removed the redundant step **Is Dedicated Tenant Record** from the playbook **03 - Enrich > Enrich Indicators (Type All)**.
