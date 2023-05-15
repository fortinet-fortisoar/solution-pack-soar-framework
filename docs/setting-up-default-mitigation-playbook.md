| [Home](../README.md) |
|----------------------|

# Setting up Default Mitigation Playbook

With the help of mitigation playbooks, you can proactively mitigate cyber intrusions, ransomware and external adversaries with destructive intent, malicious insiders, phishing attempts, and industrial control systems.

You can automate the mitigation playbooks to perform remediation actions. You can use an appropriate connector to automate an action playbook. For example, you may configure the playbook **Action - URL - Block (Indicator)** to block a URL using Fortinet's FortiGate connector.

The following image shows the **Action - URL - Block (Indicator)** playbook

![](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/res/mitigation-playbook-stock.png)

You can insert an additional step that uses Fortinet's FortiGate connector to block a URL &ndash; provided you have configured FortiGate connector.
>**TIP**: To configure and use the FortiGate connector to block a URL, refer to [Configuring Fortinet FortiGate](https://docs.fortinet.com/document/fortisoar/5.1.0/fortinet-fortigate/231/fortinet-fortigate-v5-1-0#Configuration_parameters)

Following image shows the necessary configurations required for adding the **Block URL** step.

![](https://github.com/fortinet-fortisoar/solution-pack-soar-framework/blob/release/1.1.0/docs/res/mitigation-playbook-block-url-step.png)

Click **Save** to add the step and draw the routes to complete the process. This action &ndash; of using Fortinet FortiGate to block a URL &ndash; is now ready to be included as a mitigation playbook.

To reference any playbook in an existing playbook's flow, refer to [Referencing a Playbook](https://docs.fortinet.com/document/fortisoar/7.2.0/playbooks-guide/784146/triggers-steps#Reference_a_Playbook).

| [Installation](./setup.md#installation) | [Configuration](./setup.md#configuration) | [Usage](./usage.md) | [Contents](./contents.md) |
|-----------------------------------------|-------------------------------------------|---------------------|---------------------------|