| [Home](../README.md) |
|----------------------|

# Upgrading SOAR Framework to the latest version

This page describes the prerequisites and post-upgrade changes for the SOAR Framework solution pack.

> [!Note]
> On a fresh install of FortiSOAR, `Tenant` is not a uniqueness constraint for any module. When the SOAR Framework solution pack is upgraded, `Tenant` is added as a uniqueness constraint in **Alerts**, **Cases**, **Indicators**, and **Identities**.

## Prerequisites

Before you upgrade to SOAR Framework v4.1.0, complete the following:

- Upgrade to FortiSOAR v8.0.1 or later.
- Install the Platform Utilities solution pack v1.0.1 or later.

To avoid upgrade issues, upgrade in the following order:

1. Upgrade to FortiSOAR v8.0.1 or later.
2. Install the **Platform Utilities** solution pack from [Content Hub](https://fortisoar.contenthub.fortinet.com/list.html?contentType=all&searchContent=platform%20utilities).
3. Upgrade to the SOAR Framework solution pack v4.1.0.

## Moving from global variables to the key store record

SOAR Framework v3.1.0 and later uses key store records, instead of legacy global variables and earlier key store records, for indicator extraction, exclusion, and indicator type mapping.

User-modified playbooks may still rely on the earlier key store records or legacy global variables. Edit them to use the new key store record.

> [!Important]
> Changes made through the [Indicator Extraction Configuration](./iec/indicator-extraction-wizard.md) wizard update the key store record, not the global variables.

### Editing an extraction playbook

The following example edits the **Extract Indicators (Alerts)** playbook to use the new key store record.

1. Navigate to **<picture><source media="(prefers-color-scheme: dark)" srcset="./res/icon-automation-light.svg"><source media="(prefers-color-scheme: light)" srcset="./res/icon-automation-dark.svg"><img alt="Automation icon" src="./res/icon-automation-dark.svg"></picture> Automation** <picture><source media="(prefers-color-scheme: dark)" srcset="./res/icon-chevron-light.svg"><source media="(prefers-color-scheme: light)" srcset="./res/icon-chevron-dark.svg"><img alt=">" src="./res/icon-chevron-dark.svg"></picture> **<picture><source media="(prefers-color-scheme: dark)" srcset="./res/icon-playbooks-light.svg"><source media="(prefers-color-scheme: light)" srcset="./res/icon-playbooks-dark.svg"><img alt="Playbooks icon" src="./res/icon-playbooks-dark.svg"></picture> Playbooks**.
2. Open the **Extract Indicators (Alerts)** playbook in the **03 - Enrich** collection.

> [!Note]
> Your playbooks and the steps to edit may differ.

3. Edit the step that handles indicator extraction or exclusion. In this example, the step is **Get Exclude IOCs List**.

    In the step's **Build Search Query**, set **Key** to **Equals** `sfsp-indicator-extraction-configuration`, as shown in the following image:

    ![Editing the Get Exclude IOCs List step](./res/editing-find-record-step.png)

4. Make similar changes in other playbooks, as applicable.

## Retrieving the exclusion list

Expressions that retrieve exclusion lists now read from the key store record instead of global variables.

Earlier, the following expression retrieved the exclusion list for **IP Address** indicators from global variables. Similar expressions retrieved exclusion lists for other indicator types.

```jinja
{{globalVars.ExcludeList_IPs}}
```

Use the following expression to retrieve the same list from the key store record:

```jinja
{{keystore(key_name="sfsp-indicator-extraction-configuration").jSONValue["IP Address"]}}
```

![Retrieving excluded IP addresses using the key store record](./res/retrieve-excluded-IP.png)

## Updating the URL extraction regex

SOAR Framework v4.1.0 fixes an issue where URL indicator extraction retains a backslash at the end of a URL. New installations include the corrected regex. However, an upgrade keeps your existing key store values, so update the following keys manually.

> [!Important]
> Back up all keys and regex patterns before you change their values.

### Updating the indicator regex mapping

To update the URL entry in the regex mapping key, do the following:

1. Navigate to **<picture><source media="(prefers-color-scheme: dark)" srcset="./res/icon-resources-light.svg"><source media="(prefers-color-scheme: light)" srcset="./res/icon-resources-dark.svg"><img alt="Resources icon" src="./res/icon-resources-dark.svg"></picture> Resources** <picture><source media="(prefers-color-scheme: dark)" srcset="./res/icon-chevron-light.svg"><source media="(prefers-color-scheme: light)" srcset="./res/icon-chevron-dark.svg"><img alt=">" src="./res/icon-chevron-dark.svg"></picture> **<picture><source media="(prefers-color-scheme: dark)" srcset="./res/icon-key-store-light.svg"><source media="(prefers-color-scheme: light)" srcset="./res/icon-key-store-dark.svg"><img alt="Key Store icon" src="./res/icon-key-store-dark.svg"></picture> Key Store**.
2. Open the `sfsp-indicator-regex-mapping` key.
3. In **JSON Value**, find the first entry, where `indicator_type` is `URL`.
4. Replace the existing `defang_regx` and `pattern_regx` lines in that entry with the following lines:

    ```json
    "defang_regx": "(?:https?|hxxps?|hXXps?|s?ftp|fxp|fXp)(?::\\/\\/)[^<>\\s/$.?#]+(?:\\[\\.\\]|\\.)[^\\\\<>\\s,\\\"\\']*",
    "pattern_regx": "(?:https?|s?ftp):\\/\\/[^<>\\s/$.?#].[^\\\\<>\\s,\\\"\\']*",
    ```

5. Save your changes.

### Updating the indicator extraction configuration

To update the URL pattern in the extraction configuration key, do the following:

1. Navigate to **<picture><source media="(prefers-color-scheme: dark)" srcset="./res/icon-resources-light.svg"><source media="(prefers-color-scheme: light)" srcset="./res/icon-resources-dark.svg"><img alt="Resources icon" src="./res/icon-resources-dark.svg"></picture> Resources** <picture><source media="(prefers-color-scheme: dark)" srcset="./res/icon-chevron-light.svg"><source media="(prefers-color-scheme: light)" srcset="./res/icon-chevron-dark.svg"><img alt=">" src="./res/icon-chevron-dark.svg"></picture> **<picture><source media="(prefers-color-scheme: dark)" srcset="./res/icon-key-store-light.svg"><source media="(prefers-color-scheme: light)" srcset="./res/icon-key-store-dark.svg"><img alt="Key Store icon" src="./res/icon-key-store-dark.svg"></picture> Key Store**.
2. Open the `sfsp-indicator-extraction-configuration` key.
3. In **JSON Value**, find the `URL` key.
4. Replace its value, including the square brackets, with the following array. Leave any comma after the array unchanged.

    ```json
    ["(?:https?|s?ftp):\\/\\/[^<>\\s/$.?#].[^\\\\<>\\s,\\\"\\']*"]
    ```

5. Save your changes.

## Next Steps

| [Installation](./setup.md#installation) | [Configuration](./setup.md#configuration) | [Usage](./usage.md) | [Contents](./contents.md) |
|-----------------------------------------|-------------------------------------------|---------------------|---------------------------|