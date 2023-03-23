# What's New

>**Compatible Version**: FortiSOAR v7.2.2 and later

## Playbook Enhancements

- `03 - Enrich > Extract Indicator` Playbook Changes
    - The `First Seen` and `Last Seen` date fields value will be populated for the newly created indicator
- A new  `Fetch and Link Team to Related Records` playbook under `08 - Utilities` playbook collection is added. This playbook fetches and links the team of the record to all of its related records.
- Deactivated below playbooks
    - Playbook Collection - `06 - IRP - Case Management`
        - Assign Random User to Unassigned Alerts
        -  Assign Random User to Unassigned Incidents
    - Playbook Collection - `03 - Triage` 
        - Prioritize Alerts With VIP Assets (User need to activate this playbook if user wants to create the Asset record for the hostname mentioned in the `Target Asset` field of the alert)
- The `Delete Enrichment Global Variables` playbook under `03 - Enrich` has been renamed to `Reset Enrichment Global Variables`
- The `Create Communication Record (Alert)` playbook under `06 - IRP - Communications Tracking` is modified to enable users to select email templates[FortiSOAR 7.2.2 user, Please refer to 7.2.2 Troubleshooting Scetion given below]

## Module Enhancements
- The **Default** queue record under `Queue & Shift Management > Queue Management` is now made `Inactive` by default.
**Note:** Going forward in each SOAR Framework solution pack upgrade the **Default** queue record will get `Inactive`. So if you use the **Default** queue, make sure to Reactivate the same after the upgrade.
- The `In-App Notifications` for the following Rules has beed disabled
    - Alert - Notify Creation
    - Alert - Notify Updates 
    - Incident - Notify Creation 
    - Incident - Notify Updates
- The `Re-Opened` option is now removed from the *Status* drop-down of the **Tasks** module.
- A new *Asset Risk* drop-down added to the **Asset** module with options `Minimal`, `Low`, `Medium`, `High` and `Critical`


## Resolved Issues

The following is a list of some of the important defects addressed in the **SOAR Framework v2.1.0**.

- **Bug# 888142**: The  `Prioritize Alerts With VIP Assets` playbook under `03 - Triage` playbook collection was creating assets with empty hostnames due to the hostname it is sending to child playbook `Create and Link Asset` under `08 - Utilities` playbook collection was blank. The hostname input value is fixed and the playbook no longer creates assets with empty hostname
- **Bug# 885790**: The `Navigation Panel > User Community` link was failing open FortiSOAR Community Page. The is updated to https://fortisoar.fortinet.com and geting redirected to FortiSOAR Community Page
- **Bug# 868699**: The `Compute Alert Priority Weight (Post Update - Indicator Linked)` playbook under `03 - Triage` playbook collection was failing at `Reset Priority Weight` step due incorrect variable was passed in the step. The issue is fixed by passing correct variable.
- **Bug# 860406**: The `Indicator (Manual Trigger) - Get Latest Reputation` playbook under `03 - Enrich` was updating indicator reputation to blank if there is no TIP integration available. The condition is modified to update indicator reputation to `No Reputation Available`
- **Bug# 860456**: The `User` module is not shipped in SOAR Framework solution pack. Hence, the `User` module is removed from similarity criteria from the `Similar Record Suggestions` Setting for Alerts module. 
- **Bug# 870075**: The forward slash "/" has been removed from the module link given in the "In-App" Notification content. In FortiManager, due to this extra slash  link in the In-App notification was not working.
- **Bug# 886865**: In Alert, Incidents and Warroom modules' Detailed view, Relationship tab for example. Indicators Tab in Alert SVT, used to display such a modules that are not part of excluded list. So in a situation when new custom module gets added into the FortiSOAR and not a part of excluded list, it would display under `Indicators` Tab unnecesary. To fix this Relationship widget's settings has been update to display only those module the are part of included list.

## 7.2.2 Troubleshooting Section
- For `Create Communication Record (Alert)` playbook under `06 - IRP - Communications Tracking` is modified to enable users to select email templates. This feature is introduced from FortiSOAR v7.3.0 onwards. Hence it is recommended that before upgrading to SFSP v2.1.0, you take backup of the existing playbook and replace the playbook with old one once upgrade to SFSP v2.1.0 done
- You may get issue while upgrade for connector upgrade step
    - Ensure that `SLA Calculator` connector is properly installed
    - the python packages such as pendulum, convertdate and holidays
    - If not then run the following commands
        - sudo -u nginx /opt/cyops-integrations/.env/bin/python3 /opt/cyops-integrations/.env/bin/pip3 install pendulum==2.1.2
        - sudo -u nginx /opt/cyops-integrations/.env/bin/python3 /opt/cyops-integrations/.env/bin/pip3 install convertdate==2.3.2
        - sudo -u nginx /opt/cyops-integrations/.env/bin/python3 /opt/cyops-integrations/.env/bin/pip3 install holidays==0.13