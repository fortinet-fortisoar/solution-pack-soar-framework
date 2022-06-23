# Release Information

- **Version**:  1.1.0 
- **Certified**: Yes 
- **Publisher**: Fortinet 
- **Compatible Version**: FortiSOAR v7.2.0 and above
- [Release Notes](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/release-notes.md)

# Overview 

SOAR Framework Solution Pack (SFSP) lays the foundation to use the FortiSOAR platform optimally for Incident response and automation use cases in a Security Operations Center (SOC).  

SFSP installs several modules such as alerts, incidents, and indicators along with corresponding playbooks, dashboards, reports, and widgets to make it a comprehensive solution and provide a fully functional Incident Response Platform augmented by Automation and Threat Intelligence. 

Some key benefits of SOAR Framework SP: 

- Provides standardized modules for various operations in a SOC – e.g. alerts, incidents, indicators, campaigns, and hunts
- Helps establish and follow a standardized process through playbooks for indicator extraction, enrichment, and mitigation
- Standardized dashboards and reports to help effectively monitor the setup. These dashboards and reports contain several key performance indicators(KPIs) such as Mean Time to Respond (MTTR).
- Helps build various other solution packs on top of SFSP thereby extending the system in a standardized way for various use cases, through an included framework

## Overall Design 

Let us begin with understanding the overall design/process of receiving the alerts (from various sources such as SIEM) and responding to them efficiently using automated playbooks. During the process, we will also learn about several pre-built modules, playbooks, integrations, and dashboards/reports to manage the overall SOC efficiently.  

### Information Flow

The FortiSOAR process happens in multiple steps starting from ingestion of alerts, extraction and enrichment of indicators, execution of multiple playbooks to assign various degrees of urgency to ingested alerts, and culminating in the alert’s investigation to conclude if the given alert is a false positive or true positive. 

In case of a true positive, the SOC escalates related alerts into an incident, leveraging crisis management using war rooms and several other utilities, to respond to the incident. 

The following diagram helps better understand the overall process and the subsequent explanations.

![](https://raw.githubusercontent.com/fortinet-fortisoar/solution-pack-soar-framework/release/1.1.0/docs/res/FortiSOAR-flow.svg)

1. **Data Ingestion**
    1. **Pull alerts from the data sources** - FortiSOAR, at regular intervals, pulls alerts from configured alert sources such as SIEM, EDR, or email. This process is the Alert Ingestion and it creates the alert records in the system.     
    After the alert is created, multiple playbooks (see following list) are launched to achieve intended objectives. As part of Alert Ingestion, corresponding fields are mapped into target Alert Module. Refer to [Extending Default Alert Schema](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/extending-default-alert-schema.md) for additional details. 

    2. **Create Alerts** – Alerts received from SIEM (or other sources) are converted into FortiSOAR alert records. The fields of interest such as Source IP is picked up from the source data to respective fields in FortiSOAR alert record.<br/><br/>For each newly created alert, FortiSOAR executes a playbook named **Extract Indicators**. This playbook creates **Indicator** records for the known fields of interest. For additional details, refer to [Extending Default Indicator Extraction Process](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/extending-default-indicator-extraction-process.md).

3. **Execute Playbooks** – Multiple playbooks trigger to perform following automated tasks:
    1. **Case Management** - Case Management automates processes like adding users as case owners, tracking SLA and resolution timelines, using playbooks. It also contains playbooks that resolve an alert by taking appropriate action or marking it as an **incident** and escalating it.
    2. **Indicator Extraction & Enrichment** - After creating an indicator record, FortiSOAR triggers appropriate playbooks such as **Indicator (TypeDomain) – Get Reputation** to gather more context (a.k.a Enrichment) and to compute the reputation of the given indicator.   
    Enrichment happens using various Cyber Threat Intelligence(CTI) sources such as VirusTotal, FortiGuard, or URLVoid; and also from sources such as Active Directory® for user context enrichment. For additional details, refer to [Extending Default Indicator Enrichment Process](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/extending-default-indicator-enrichment-process.md) section.
        >**NOTE**: After the completion of Indicator extraction and enrichment, the alert is ready for further investigation. This state is internally identified as `state=ready to investigate`. Here, some playbooks trigger as a response to specific type of alert. These are termed as **Use Case Playbooks**. The playbook collection named “**02 – Use Cases**” contains multiple such response playbooks. Alternatively, some Solution Packs(SP) deploy their respective response playbooks in a collection named as `02 - Use Case - <intent>`. For example **02- Use Case - Brute Force Attack** which contain playbooks for responding to Brute Force Attack alerts.

    3. **Triage** - Triaging is identifying of the criticality of data and assets, the severity of the incident, deciding containment strategies, following the escalation matrix, and then acting on the defined isolation and blocking strategies.     
    Suppose there are multiple alerts received, signifying an incident &ndash; a threat actor is attempting to gain access to two computers (assets) in your network; one of the assets is an endpoint with sensitive data and the other is a decoy. In this case, while triaging, you assign higher priority to the endpoint with sensitive data.

    4. **Investigation Playbooks** - After a successful triage, analysts may launch specific investigation playbooks manually, or devise specific conditions that could trigger these playbooks automatically. These playbooks are designed to conduct detailed investigation and escalate alerts into an incident, if required. For additional details, refer to [Building Investigation/Response Playbook](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/building-investigation-response-playbook.md).

    5. **Action** - Actions may include asset mitigation by isolation, blocking domains and URLs through firewalls, and blocking or disabling users and IP addresses. SFSP includes a host of Action playbooks that you can include in your playbooks as mitigation or corrective responses. For additional details, refer to [Action Playbook Collection](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/contents.md#actions-playbook-collection).

    6. **Hunt** - Hunt playbooks search the presence of specified domains, files, or other indicators in the organization. For example, a given File &ndash; identified through filehash &ndash; present on any computer in the organization.

4. **Update Alerts** - The intelligence gathered from indicator investigation is fed to the alert source (SIEM, EDR, or similar alert sources) to prevent similar threats in the future.<br/>
    >**NOTE**: Marking an alert as **Closed** invokes a corresponding [close source alert](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/contents.md#06---irp---case-management) playbook. This playbook, by default, simply prompts you to close the alert at the source; however, you must modify that to use the respective product's connectors (such as FortiSIEM) to invoke the closure action. This way you can update the source systems to your desired state.

5. **Escalate** - At the end of this cycle, the given alert is either marked as **False Positive** and **closed** or marked as **True Positive** and **Escalated into an Incident**. Note, the Escalation into an incident by default is a manual step (by clicking **Escalate** button), but the same can also be automated via invoking **Escalate to Incident Playbook** into the respective response playbooks.

6. **Crisis Management** - To avert a crisis, it is customary and an obvious course of action to bring in all the stakeholders together to formulate the next plan of action. The **War Room** helps bring together everyone who can help solve the problem. For example, in case of an **Incident**, an organization may have to:
    - Issue a statement, for which they need their Legal team
    - Gauge the financial redressal required, for which presence of the Finance team is crucial
    - Rope in the Human Resources(HR) team, if employees are involved   

    A **War Room** in this scenario brings together all the above teams and help devise a more intuitive plan of action.

<!-- - **Incident Response** - These playbooks help plan a response to an incident such as a malware attack. -->

## Additional Resources 

- [Extending Default Alert Schema](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/extending-default-alert-schema.md)
- [Configuring Alert Ingestion Process](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/configuring-alert-Ingestion-process.md)
- [Extending Default Indicator Extraction Process](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/extending-default-indicator-extraction-process.md)
- [Extending Default Indicator Enrichment Process](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/extending-default-indicator-enrichment-process.md)
- [Building Investigation/Response Playbook](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/building-investigation-response-playbook.md)
- [Setting up Default Mitigation Playbooks](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/setting-up-default-mitigation-playbook.md)
<!-- * [Setting up Default Hunt Playbooks](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/setting-up-default-hunt-playbook.md) -->

## Next Steps

| [Installation](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/setup.md#installation) | [Configuration](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/setup.md#configuration) | [Usage](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/usage.md) | [Contents](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/contents.md) |
|--------------------------------------------|----------------------------------------------|------------------------|------------------------------|
