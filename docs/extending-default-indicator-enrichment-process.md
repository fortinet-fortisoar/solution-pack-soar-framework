| [Home](../README.md) |
|----------------------|

# Extending Default Indicator Enrichment Process

For every indicator &ndash; file URL, hash, domain, IP address, user &ndash; there is a corresponding enrichment playbook that goes through multiple intelligence platforms and other processes, collects the data, and puts that information in a formatted manner to the indicator record.

In the default Indicator Enrichment process,

- The playbooks run after indicator creation
- The playbooks take the *Type* and *Value* from the indicators
- It reaches out to various sources to set the reputation in the indicator record

Taking the data from these sources it formats and populates the description field with enrichment data.

While these playbooks provide a strong foundation for enriching indicators in FortiSOAR, multiple configurations and subsequent playbook actions become available even after deployment. Going beyond investigation, you can add additional playbooks to run the indicators through various sources and services to get reputation and another context about indicators.

>**NOTE**: With the new "Pluggable" enrichment in place, the enrichment process is now faster and more optimized. We recommend using it to augment or enhance your indicator enrichment process.

# Using the "Pluggable" Indicator Enrichment

"Pluggable" Indicator Enrichment process uses the playbooks contained within installed connectors to enrich the context of an indicator.

This enrichment process is triggered when an indicator is created. On creation, the playbook **Enrich Indicators (Type All) playbook** runs and puts the following sequence in motion.

1. **Search Tagged Playbooks**: The playbook *Enrich Indicators (Type All)* searches for installed connector playbooks with specific tags using **Update/Initialize Indicator Enrichment Global Variables** playbook. For example, if the indicator is of the type *URL*, this playbook looks for the tag `URL_Enrichment`; for indicators of type *IP Address* it looks for the tag `IP_Enrichment`; for indicators of type *File Hash* it looks for the tag `FileHash_Enrichment`; and so on.

2. **Configuration Check**: Once the playbooks with appropriate tags are identified, the *Update/Initialize Indicator Enrichment Global Variables* playbook checks if the corresponding connectors are configured. For this purpose, it runs **Retrieve Configured Enrichment Connectors** playbook.

3. **Check Playbook IRI Global Variable**: If the connectors are configured, *Update/Initialize Indicator Enrichment Global Variables* playbook checks the global variables &mdash; in the format `<indicator type>_Enrichment_Playbooks_IRIs` &mdash; containing the associated playbooks IRI, and creates the variable if not found. For example, for indicator of type *URL* it checks for the global variable `URL_Enrichment_Playbooks_IRIs` and creates the global variable when not found.

4. **Update Playbook IRI**: The *Update/Initialize Indicator Enrichment Global Variables* playbook adds the associated playbook IRIs to the corresponding global variable. For example, the IRIs, of playbooks tagged with `URL_Enrichment`, are added to the global variable `URL_Enrichment_Playbooks_IRIs`.

5. **Add/Remove Existing Playbook IRIs**: In a situation when user adds new/custom enrichment playbook or remove/inactivate the  existing enrichment playbooks from the sample collection then it is required to reset the enrichment global variable by executing the `Reset Enrichment Global Variables` playbook in *Indicator* module without selecting any indicator record. 

6. **Enrichment Begins**: The playbook **Enrich Indicators (Type All)** triggers the associated connector's enrichment playbooks who then return the following CTI (Cyber threat intelligence) information:

    - CTI name
    - CTI scores
    - Verdicts
    - Source data
    - Field mapping
    - Enrichment summary
