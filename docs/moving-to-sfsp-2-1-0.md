| [Home](../README.md) |
|----------------------|

# Upgrade SOAR Framework from v2.x.x to v2.1.0 and later

Before upgrading SOAR Framework to v2.1.0 and later, perform the following steps:

1. Add following key-value pair in `Indicator_Type_Map` global variable. To add a key-value pair, refer to the section [Extending Default Alert Schema](./extending-default-indicator-extraction-process.md#extending-default-alert-schema):

    ```json
    {
    "iPAddresses": "IP Address",
    "fileHashes": "FileHash-MD5"
    }
    ```

2. To upgrade the SOAR Framework solution pack to version 2.1.0 and later on FortiSOAR v7.2.2, perform the following steps:
    <ol type="a">
      <li>Take a backup of <strong>Create Communication Record (Alert)</strong> playbook under the collection <em>06 - IRP - Communications Tracking</em>.</li>
      <li>Add the the key-value pair as mentioned in step 1.</li>
      <li>Replace <strong>Create Communication Record (Alert)</strong> playbook under the collection <em>06 - IRP - Communications Tracking</em> with the back up copy you have.</li>
    <ol>

| [Installation](./setup.md#installation) | [Configuration](./setup.md#configuration) | [Usage](./usage.md) | [Contents](./contents.md) |
|-----------------------------------------|-------------------------------------------|---------------------|---------------------------|