| [Home](../README.md) |
|----------------------|

# Usage

This section attempts to explain how SOAR Framework Solution Pack and its features address your needs. It gives general directions for understanding various ways in which this solution pack can be used. Also, we have included some really simple steps that act as test cases to understand the SOAR Framework construct.

## Standardized Modules
SOAR Framework Solution Pack provides standardized modules for various operations in a Security Operations Center. Following modules are part of, and provided by, FortiSOAR:

1. Alerts
2. Announcements
3. Assets
4. Campaigns
5. Communication
6. Events
7. Cases
8. Indicators
9. War Rooms

> [!NOTE]
> On a fresh install of FortiSOAR&trade;, `Tenant` is not a uniqueness constraint for any of the modules. However, when SOAR Framework Solution Pack is upgraded, `Tenant` is added as a uniqueness constraint in `Alerts`, `Cases`, `Indicators`, and `SLA Templates`.

## Standardized Process for Working with Alerts

SOAR Framework Solution Pack establishes a standard process through playbooks for indicator extraction, enrichment, and mitigation.

### Creating Alerts

> [!TIP]
>
> To manage SLA and view an SLA timer on an alert's detail view, install the [SLA Management](https://fortisoar.contenthub.fortinet.com//list.html?contentType=solutionpack&searchContent=Sla%20management) solution pack, **_before_** triggering alert ingestion or creation.

## Standardized Process for Working with Indicators

SOAR Framework Solution Pack establishes a standard process through playbooks for indicator extraction, enrichment, and mitigation.

### Validating Indicator Extraction

Here we use known suspicious or malicious indicators and perform some simple steps to establish that indicators are being extracted.

1. Create an alert of type *Brute Force Attempt*.
2. Specify the source IP as `2.58.56.16`.
3. Navigate to **Alerts** and open the newly created alert.

#### Expected Result

An indicator of type *IP Address* and value `2.58.56.16` is created and linked to this alert.

### Validating Indicator Enrichment

Here we use the same IP address and perform some simple steps to establish that indicators are being enriched &ndash; we have the indicator's reputation.

1. Scroll down on the newly created alert page.
2. Open the indicator record for `2.58.56.16`.

#### Expected Result

1. Indicator reputation is now **Malicious**.
2. The **Reputation** is established and is neither *Empty* nor *TBD*.

### Validating Indicator Mitigation

Here we use the same IP address &ndash; with its newfound reputation &ndash; and perform some simple steps to establish that the "threat" has been mitigated by successfully blocking the IP address.

1. Select the indicator record checkbox for `2.58.56.16`.
2. Click **Execute** above the indicator record.
3. Select **Block IP Address** from the drop-down.

Alternatively,
1. Click the indicator record for `2.58.56.16` to open it.
2. Click the button **Block IP Address**.

#### Expected Result

1. The playbook **Block IP** is launched.
2. A prompt asks you to enter a blocking reason.
3. The playbook follows the course of blocking and marks the indicator status as **Blocked**.

| [Installation](./setup.md#installation) | [Configuration](./setup.md#configuration) | [Contents](./contents.md) |
|-----------------------------------------|-------------------------------------------|---------------------------|
