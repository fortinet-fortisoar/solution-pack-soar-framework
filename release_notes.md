# What's New

>**Compatible Version**: FortiSOAR v7.2.2 and later

## Playbook Enhancements

- New playbook `Fetch and Link Team to Related Records` has been added under the collection `08 - Utilities` 
    - When triggered, this playbook fetches a team of the selected record and links it to all related records
        > **For Example**: Teams `TeamA` and `TeamB` are assigned to `Alert-1` which further links to five indicators. Upon running this playbook, it also links teams `TeamA` and `TeamB` to the five associated indicators.

- Modified `Extract Indicator` playbook under the collection `03 - Enrich`
    - `First Seen` and `Last Seen` date fields are now present in the newly created indicator
    - Indicators are now created from newly added `IP Addresses` and `File Hashes` fields in the **Alert** module
    - In case of multi-tenancy, a tenant from the alert record is also assigned to the indicator
    - Email indicators that are part of the exclude domain indicators list (`Excludelist_Domains` global variable) are now ignored

- Modified `Create Communication Record (Alert)` playbook under the collection `06 - IRP - Communications Tracking`
    - User can now select email templates while sending an email from **Alert** detail view

- Modified `Alert - Escalate To Incident` playbook under the collection `06 - IRP - Case Management 
    - In case of multi-tenancy, this playbook assigns escalated alert tenant value to a newly created Incident record 

- Renamed `Delete Enrichment Global Variables` playbook to `Reset Enrichment Global Variables` under the collection `03 - Enrich`

- Deactivated the following playbooks:
    - `Assign Random User to Unassigned Alerts` and `Assign Random User to Unassigned Incidents` playbooks under the collection `06 - IRP - Case Management`
    - `Prioritize Alerts With VIP Assets` under collection `03 - Triage`   
    >**NOTE** Users need to activate this playbook if they want to create the asset record for the hostname mentioned in the alert's `Target Asset` field

## Module Enhancements

- **Queue Management Module**
    - By default, the **Default** queue record now is `Inactive`

        >**NOTE**: In every SOAR Framework solution pack upgrade, the **Default** queue record is marked `Inactive`. To use the **Default** queue, you need to activate it.
    
- **Tasks Module**
    - `Re-Opened` dropdown item is removed from the *Status* drop-down

- **Asset Module**
    - A new *Asset Risk* drop-down was added with the options `Minimal`, `Low`, `Medium`, `High`, and `Critical`
    
- **Event Module**
    - Updated System View Template (SVT) as per the module's best practices

- **Alert Module**
    - Added new `Resolved Automatedly` hidden boolean field
    - Added new `Recommendation setting` for Playbook suggestion based on Name and Type of **Alerts**
    - Added new `IP Addresses` and `File Hashes` fields

        >**NOTE** `Indicator_Type_Map` global variable is also updated with the `IP Addresses` and `File Hashes` fields. These fields are now also used during indicator extraction

- **Incident Module**
    - Added new `Recommendation Setting` for playbook suggestion based on Name and Type of **Incidents**

- Added new `Key Store` module. You can find it under the `Resources` navigation panel


## Rules Enhancements

- `In-App Notifications` have been disabled for following `Rules`

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

- Asset records with empty hostnames were being created by the `Prioritize Alerts With VIP Assets` playbook under the collection `03 - Triage`. Now, the hostname input value is correctly passed so asset records have correct hostnames

- Updated the FortiSOAR Community page URL to fix the Page not found error while accessing FortiSOAR Community Page from `Navigation Panel > User Community`.

- When an appropriate Threat Intel connector is not present, the `Indicator (Manual Trigger) - Get Latest Reputation` playbook under the collection `03 - Enrich` updates the indicator reputation to `No Reputation Available` instead of `blank`

- Fixed `Relationship widget` configuration in *Alert*, *Incidents*, and *Warroom* detailed view to show modules that are part of the included list of the widget configuration

