| [Home](../README.md) |
|----------------------|

# Upgrading SOAR Framework v2.x.x to latest version

> [!Note]
> On a fresh install of FortiSOAR&trade;, `Tenant` is not a uniqueness constraint for any of the modules. However, when SOAR Framework Solution Pack is upgraded, `Tenant` is added as a uniqueness constraint in **_Alerts_**, **_Incidents_**, and **_Indicators_**.

## Prerequisites

Before upgrading to SOAR Framework v3.2.1 and later, you must

- Upgrade to FortiSOAR `v7.6.2` or later

- Install Platform Utilities solution pack `v1.0.1` and later

Hence, we recommend that users perform the upgrade of their FortiSOAR instances in the following order to avoid upgrade issues:

1. Upgrade to FortiSOAR v7.6.2.

2. Install the **Platform Utilities** solution pack from [Content Hub](https://fortisoar.contenthub.fortinet.com//list.html?contentType=all&searchContent=platform%20utilities).

3. Upgrade to the SOAR Framework solution pack v3.2.1.

## Moving from Global Variables to Key Store Record

SOAR Framework `v3.1.0` and later uses the new keystore records instead of old keystore records and legacy global variables for indicator extraction, exclusion, and indicator type mapping.

There may be cases where user-modified playbooks are still reliant on the old keystore records or legacy global variables. This section helps users to edit their user-modified playbooks so as to use the new keystore record.

> [!Important]
> Configuration changes made through the [*Indicator Extraction Configuration*](../docs/iec/indicator-extraction-wizard.md) wizard updates the key store record and not the Global Variables.

### Editing Extraction Playbooks - An Example

Let us consider the playbook **Extract Indicators (Alerts)** as an example. We will edit this playbook to refer to the new keystore record.

1. Navigate to **Automation** ![automation icon](./res/icon-automation.svg) ![next](./res/icon-chevron-right.svg) **Playbooks** ![playbook icon](./res/icon-playbooks.svg).

2. Open the playbook **Extract Indicators (Alerts)**, under the collection *03 - Enrich*.

> [!Note]
> Your playbooks and the corresponding steps to be edited may be different.

3. Edit the step that handles indicator extraction or exclusion. In this example, that step is **Get Exclude IOCs List**.

    The *Build Search Query* for this step is shown in the following image:

    ![Editing Get Exclude IOC list](./res/editing-find-record-step.png)

    **Key** *Equals*`sfsp-indicator-extraction-configuration`

4. Similar changes may be required in other playbooks, as applicable.

## Retrieving Exclusion List

Earlier, the following expression helped retrieve excluded list of **IP addresses** using global variables:

```jinja
    {{globalVars.ExcludeList_IPs}}
```

Similar expressions retrieved exclude list for other indicator types.

Now, the following expression helps retrieve excluded list of **IP addresses** using the new keystore record:

```jinja
    {{keystore(key_name="sfsp-indicator-extraction-configuration").jSONValue["IP Address"]}}
```

![Retrieving excluded IPs using the new keystore](./res/retrieve-excluded-IP.png)

# Next Steps

| [Installation](./setup.md#installation) | [Configuration](./setup.md#configuration) | [Usage](./usage.md) | [Contents](./contents.md) |
|-----------------------------------------|-------------------------------------------|---------------------|---------------------------|