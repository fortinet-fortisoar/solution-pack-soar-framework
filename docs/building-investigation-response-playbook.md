| [Home](../README.md) |
|----------------------|

# Building Investigation/Response Playbook

Playbooks in FortiSOAR help you automate your security processes across external systems while respecting the business process required for your organization to function. Playbooks included with SOAR Framework Solution packs can be customized to follow an organization's current procedures while leveraging the automation capabilities of FortiSOAR.

You can build specific playbooks that help you in investigation or respond to various threats. Following pointers must be noted when creating investigation/response playbooks:

- You can trigger your playbook &ndash; manually, or automatically for a certain alert type.
    * **Manual Trigger** - Playbooks with manual triggers are available to run as soon as they are active; after which these playbooks appear under the **Execute** drop-down list. You can also specify a condition when this playbook becomes visible &ndash; is available as one of the actions under the **Execute** drop-down list. E.g. the following screen shows that the playbook becomes visible when following conditions are met:

        >Indicator *Type* is *URL*  
        >*Status* is not *Blocked*.

        ![](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/res/playbook-manual-trigger-display-conditions.png)

        * You can trigger a playbook, manually, based on a selected module without selecting a record in the specified module. E.g. a manual trigger to check for new alerts from a SIEM tool, can be run globally on the **Alerts** module.

    * **Automatic Trigger** - Intuitively, you may use a condition that triggers, after the indicators are extracted and alerts updated. SFSP includes playbooks that ensure indicator extraction.

        >On update  
        >*State* *is changed*     
        >*State* is *Indicator Extracted*

        ![](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/res/post-update-state-indicator-extracted.png)

- Investigation/Response playbooks should typically be executed, once indicator extraction and enrichment is complete. Hence, a response playbook's trigger should be set to

    >On Update  
    >*State* is *Indicator Extracted*
    
    ![](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/res/on-update-state-indicator-extracted.png)

    This step ensures that your investigation/response playbook is executed only after indicators are extracted and enriched.

- SFSP includes an escalation playbook that escalates an alert to an incident. You may want to reference that playbook, in your response flow, instead of creating a new playbook that performs the same actions.

    ![](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/res/reference-playbook-escalate-to-incident.png)