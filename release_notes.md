# What's New
## Enhancements
## Playbook Enhancements
- The enrichment playbook **Indicator (Type File - MD5) - Get Reputation** from the **02 - Enrich** collection now also enriches file hashes SHA256 and SHA1
- New playbooks added to [**08 - Utilities**](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/contents.md#utilities-playbook) playbook collection:
    - **Activate Inactive Users** with **Activate inactive users - Update user status** as a subroutine playbook    
    This playbook finds all inactive FortiSOAR users and activates them
    - **Indicator - Import Bulk Indicator** - This playbook imports indicators in bulk     

## New Connector
- With the help of the new IP Quality Score(IQS) connector, the playbook **Indicator (Type Email) - Get Reputation** now gets email reputation from IQS database
    - The emails are considered *Malicious* if 
        - The IQS score is more than `90` OR
        - If the email addresses have been exposed in a data breach
    - The emails that do not meet the above criteria are considered *Suspicious*

## UI Changes
- The **Communications** module has been added under **Incident Response** navigation menu
- The **Overview** dashboard now displays a **Closure Reason in Last 30 Days** chart with **False Positive** as one of the legends

### Messages
- After the creation of an indicator, a message with a progress indicator (spinner) now informs the users that indicator enrichment is in progress 
- When an alert is closed, the alert screen now displays a message stating that the alert is resolved

## Bugfixes
- Visibility conditions on email alerts display following details when the alert type is **Phishing**
    - Reporter details
    - Email details
- The playbook **Indicator (Type IP) - Get Reputation** gets WHOIS information from WHoisRDAP and VirusTotal and displays it on indicator screen
- Alert's text fields' *Length Constraint* is now increased from 255 to 1024. Following fields' *Length Constraint* has been further increased from 255 to 2048
    - `Email Subject`
    - `File Path`
- Alert's `Source ID` fields *Length Constraint* has been removed
- **Resolved Alert** playbook now prompts the users to select a resolution reason
- The playbook **Prioritize Alerts With VIP Assets** under the collection **03 - Triage** collection now creates assets only when input data is present

