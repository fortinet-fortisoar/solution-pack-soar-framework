| [Home](./README.md) |
|----------------------|

# What's New

| Compatible Version | FortiSOAR v7.4.1 and later |
|--------------------|----------------------------|

| NOTE | If you have updated any of the System View Templates(SVTs), Module Metadata (MMD), and playbooks, ensure to take a backup before updating SOAR Framework solution pack, as any changes that you have made will be overwritten. |
|------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

## Playbook Enhancements

- The **Extract Indicators** playbook in the *03 - Enrich* collection now renders all URLs found in the *Email Body* field of the alert, ineffective (defangs the links and URLs)

## Module Enhancements

### Assets

- Following fields and picklists have been added to the Assets Module Metadata (MMD)

    - **Fields**

        1. Network - Text Field
        2. Subnet - Text Field
        3. Firmware - Text Field
        4. Vendor - Text Field
        5. Product - Text Field
        6. Asset - Many To Many Field
        8. ESPZone - Text Field
        9. Facility - Text Field
        10. Protocol - Multi Select Picklist Field
        11. Level - Picklist Field
        12. Zone - Picklist Field
        13. Asset Type - Picklist Field
        14. Vulnerability Risk Status - Picklist Field

    - **Picklists**
        1. Asset Level
        2. Asset Protocol
        3. Asset Type
        4. Asset Zone
        5. Vulnerability Risk Status

- Two new tabs **Asset Change Activity** and **Advisories & KEVs** have been added to the *Asset Detailed View*. These tabs become visible only when the asset *Type* is not `Other`.
- Removed the **Companies** module from the *Correlations* tab in the *Assets Detailed View*.

### Alerts

- Following widgets are now a part of the **Alerts** module and its detailed view:

    - Visual Correlation
    - Record Distribution widget &ndash; becomes visible only when the linked asset *Type* is not `Other`.

- A new tab **Recommended ATT&CK Mitigation** under *Alert* detailed view and becomes visible only when the *Technique ID* field is not `empty` or `null`.

- A new *Rule* field is added to the alert module and its detailed view. This field becomes visible only when the *Rule* field is not empty and contains the name of the rule that triggered an alert's creation.

### Incidents

- A new **Record Distribution** widget in *Incident* detailed view becomes visible only when the linked asset *Type* is not `Other`.

## Resolved Issues

- The comment containing the link **Go to War Room** now correctly navigates to the newly created War Room record. This comment is added by the **Set up War Room from Incidents** playbook under the collection *06 - IRP - War Room*.