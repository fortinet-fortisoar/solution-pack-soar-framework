| [Home](../README.md) |
|----------------------|

# Upgrading from SOAR Framework v2.x.x to latest version

Before upgrading SOAR Framework, perform the following steps:

Add following key-value pair in `Indicator_Type_Map` global variable. To add a key-value pair, refer to the section [Extending Default Alert Schema](./extending-default-indicator-extraction-process.md#extending-default-alert-schema):

- To extract indicators from alerts, add (append) the following JSON in `Indicator_Type_Map`

    ```JSON
    {
        "iPAddresses": "IP Address",
        "fileHashes": "FileHash-MD5"
    }
    ```

- To extract indicators from newly-created incidents (not escalated from alerts), add (append) the following JSON in `Indicator_Type_Map`

    ```JSON
    {
        "dLLName": "Process", 
        "filehash": "FileHash-MD5", 
        "processName": "Process", 
        "destinationIP": "IP Address", 
        "sourceIP": "IP Address", 
        "receipientEmailAddress": "Email Address" ,
        "targetAsset": "Host", 
        "senderDomain": "Domain", 
        "senderEmailAddress": "Email Address"
    }
    ```

- The **Key Store** module is now a replacement to using global variables as per the following table:

    | Global Variable Name             | Key Store Record               |
    |:---------------------------------|:-------------------------------|
    | No corresponding global variable | *sfsp-excludelist-cidr-ranges* |
    | `Excludelist_IPs`                | *sfsp-excludelist-ips*         |
    | `Excludelist_URLs`               | *sfsp-excludelist-urls*        |
    | `Excludelist_Domains`            | *sfsp-excludelist-domains*     |
    | `Excludelist_Files`              | *sfsp-excludelist-files*       |
    | `Excludelist_Ports`              | *sfsp-excludelist-ports*       |


<table>
    <th>NOTE</th>
    <td>On a fresh install of FortiSOAR&trade;, <code>Tenant</code> is not a uniqueness constraint for any of the modules. However, when SOAR Framework Solution Pack is upgraded, <code>Tenant</code> is added as a uniqueness constraint in <strong><em>Alerts</em></strong>, <strong><em>Incidents</em></strong>, and <strong><em>Indicators</em></strong>.</td>
</table>

# Next Steps

| [Installation](./setup.md#installation) | [Configuration](./setup.md#configuration) | [Usage](./usage.md) | [Contents](./contents.md) |
|-----------------------------------------|-------------------------------------------|---------------------|---------------------------|