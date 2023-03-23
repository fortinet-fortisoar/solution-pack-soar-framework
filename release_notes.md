# What's New

>**Compatible Version**: FortiSOAR v7.2.2 and later

## Playbook Enhancements

- Modified `Extract Indicator` playbook under the collection `03 - Enrich`
    - `First Seen` and `Last Seen` date fields will be populated in newly created indicator
    - Indicators will be created from newly added `IP Addresses` and `File Hashes` fields in **Alert** module
    - In case of multi-tenancy, tenant from Alert record will be assigned to an indicator as well
    - Email indicators will be ignored that are part of exclude domain indicators list (`Excludelist_Domains` global variable)

- Modified `Create Communication Record (Alert)` playbook under the collection `06 - IRP - Communications Tracking`
    - User can now select an email templates while sending an email from **Alert** detail view

- Modified `Alert - Escalate To Incident` playbook under the collection `06 - IRP - Case Management` 
    - In case of multi-tenancy, this playbook will assign escalated Alert(s) tenant value to an newly created Incident record 

- New playbook `Fetch and Link Team to Related Records` has been added under the collection `08 - Utilities` 
    - when triggered, it will fetch a team of the selected record and link it to all related records
    - e.g. Team 'TeamA' and 'TeamB' are assigned to 'Alert-1' and 5 Indicators are also linked to 'Alert-1'. Upon running above playbook, it will also link team 'TeamA' and 'TeamB' to associated 5 indicators.

- Renamed `Delete Enrichment Global Variables` playbook to `Reset Enrichment Global Variables` under the collection `03 - Enrich`

- Deactivated below playbooks
    - `Assign Random User to Unassigned Alerts` and `Assign Random User to Unassigned Incidents` under the collection `06 - IRP - Case Management` 
    - `Prioritize Alerts With VIP Assets` under collection `03 - Triage`   
    **NOTE** User need to activate this playbook if user wants to create the Asset record for the hostname mentioned in the `Target Asset` field of the alert

## Module Enhancements

- **Queue Management Module**
    - By default, the **Default** queue record will be `Inactive`
    **NOTE** In every SOAR Framework Solution Pack upgrade the **Default** queue record will be marked `Inactive`. Re-activate, if you use the **Default** queue
    
- **Tasks Module**
    - `Re-Opened` dropdown item is removed from the *Status* drop-down

- **Asset Module**
    - A new *Asset Risk* drop-down added with an options `Minimal`, `Low`, `Medium`, `High` and `Critical`
    
- **Event Module**
    - Updated SVT as per module best practices

- **Alert Module**
    - Added new `Resolved Automatedly` hidden boolean field
    - Added new `Recommendation setting` for Playbook suggestion based on Name and Type of **Alerts**
    - Added new `IP Addresses` and `File Hashes` fields 
    **NOTE** `Indicator_Type_Map` global variable is also updated with `IP Addresses` and `File Hashes` fields. These fields will also be used during indicator extraction

- **Incident Module**
    - Added new `Recommendation Setting` for Playbook suggestion based on Name and Type of **Incidents**

- Added new `Key Store` module. You can find it under `Resources` navigation panal


## Rules Enhancements

- `In-App Notifications` has been disabled for following `Rules`
    - Alert - Notify Creation
    - Alert - Notify Updates 
    - Incident - Notify Creation 
    - Incident - Notify Updates

## Introduced Reference Block(s) 

- Introduced following Out of the box reference blocks:
    - Approval-Based Decision 
    - Bulk ingest records using the 'Ingest Bulk Feed' Step
    - Check if an IP address is Internal or External
    - Condition-based Post-Create Trigger 
    - Condition-based Post-Update Trigger
    - Create and Link Asset to Alert
    - Execute Playbook Step using Do-Until Loop
    - Execute Playbook Step using Parallel Looping
    - Execute Playbook step using Sequential Looping
    - Execute Playbook using Mock Data
    - Extracting Artifacts from a String 
    - Fetch Emails From Particular Inbox in Exchange
    - Handling Record Uniqueness (No Change Needed To Existing Record)
    - Handling Record Uniqueness (Stop Process when Duplicate Record Found)
    - Handling Record Uniqueness (Update Existing Record - All Fields)
    - Handling Record Uniqueness (Update Existing Record - Only Selected Fields)
    - Make a REST API Call
    - Manual Trigger using User Input Prompt
    - Manual Trigger with Visibility Condition
    - Manual Trigger without Selecting Records
    - Posting a Message on Triggering Record (using Create Record Step)
    - Posting a Message on Triggering Record (using Step Utilities)
    - Set New Variable to Store Record Information 
    - Using Code Snippet
    - Using Custom API Endpoint Trigger
    - Using Decision Step
    - Using Ignore Error to Avoid Playbook Failure
    - Using Manual Input Step
    - Using Manual Task Step
    - Calculate Severity using ResolveRange

## Resolved Issues

- Asset record with empty hostnames were created by `Prioritize Alerts With VIP Assets` playbook under the collection `03 - Triage`. Now, the hostname input value is correctly passed
- Page not found error occured while accessing FortiSOAR Community Page from `Navigation Panel > User Community`. Corrected FortiSOAR Community Page URL
- Indicator reputation was set to `blank` in case of absence of TIP connector. Now, `Indicator (Manual Trigger) - Get Latest Reputation` playbook under the collection `03 - Enrich` will update indicator reputation to `No Reputation Available`
- Fixed `Relationship widget` configuration in Alert, Incidents and Warroom detailed view to show modules which are part of included list of widget configuration

