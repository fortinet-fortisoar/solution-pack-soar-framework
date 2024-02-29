| [Home](../README.md) |
|----------------------|

# Setting up Ownable Settings

- Starting from SFSP version 2.2.1, the team ownable setting for out-of-the-box modules is Disabled by default to improve performance.
- If you need to segregate records for different teams, it's recommended to Enable the team ownable option for specific modules.
- For instance, let's say your organization has two teams: L1 and L2.
- L1 is responsible for analyzing alerts based on extracted indicators, while L2 handles escalated incidents from L1.
- In this scenario, L2 needs ownership of alerts, incidents, and indicators for access.
- However, L1 should not have ownership of escalated incident records to maintain separation.
- Thus, members of L1 won't have ownership of incident records that are escalated.

You will also need to set a hierarchy among the team like shown below. 



| [Installation](./setup.md#installation) | [Configuration](./setup.md#configuration) | [Usage](./usage.md) | [Contents](./contents.md) |
|-----------------------------------------|-------------------------------------------|---------------------|---------------------------|