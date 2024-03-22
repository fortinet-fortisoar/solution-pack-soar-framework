| [Home](../README.md) |
|----------------------|

# Managing `Team Ownable` Settings

Starting SOAR Framework Solution Pack version `v2.2.1` and later, the team ownable setting for out-of-the-box modules is **_`disabled`_** by default to improve performance. For *War Room*, however, it has been enabled from SOAR Framework `v2.3.0`.

However, if you have multiple teams, you may want to **_`enable`_** this option to control the teams' access to various records.

___
Example
-----------
Considering your organization has 2 analyst teams - *Forts* and *Spears*.

- **Forts** work with Alert and Indicator modules
- **Spears** work with Alert, Incident, and Indicator module.

- **Forts** analyze alerts based on extracted indicators and **Spears** are responsible for handling incidents escalated by Forts.

To achieve this segregation **`Team Ownable`** parameter must be set to `true` for these modules. For more information, refer to the section [Security Management](https://docs.fortinet.com/document/fortisoar/7.4.3/administration-guide/202940/security-management#Security_Management) on FortiSOAR&trade; platform documentation.
___

## Next Steps

| [Installation](./setup.md#installation) | [Configuration](./setup.md#configuration) | [Usage](./usage.md) | [Contents](./contents.md) |
|-----------------------------------------|-------------------------------------------|---------------------|---------------------------|