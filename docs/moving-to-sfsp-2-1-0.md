# Upgrade SOAR Framework from v2.x.x to v2.1.0

If you upgrading this solution pack on FortiSOAR v7.2.2. Please refer to the following steps:
- For `Create Communication Record (Alert)` playbook under `06 - IRP - Communications Tracking` is modified to enable users to select email templates. This feature is introduced from FortiSOAR v7.3.0 onwards. Hence it is recommended that before upgrading to SFSP v2.1.0, you take backup of the existing playbook and replace the playbook with old one once upgrade to SFSP v2.1.0 done
- You may get issue while upgrade for connector upgrade step
    - Ensure that `SLA Calculator` connector and its dependencies are installed