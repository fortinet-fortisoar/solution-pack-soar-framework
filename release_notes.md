| [Home](./README.md) |
|---------------------|

# What's New

<table>
    <tr>
        <th>Compatible Version</th>
        <td>FortiSOAR v7.4.1 and later</td>
    </tr>
</table>

<table>
    <tr>
        <th>NOTE</th>
        <td>Before updating the SOAR Framework solution pack, make sure to back up any modifications you have made to <strong>System View Templates (SVTs)</strong>, <strong>Module Metadata (MMD)</strong>, and <strong>playbooks</strong>. This is essential because updating the solution pack overwrites any changes you might have made.</td>
    </tr>
</table>

## Module Enhancements

### Alerts

- Marked the `Hide Empty Fields` checkbox `true` by default in Alert Detailed View

### Indicators

- Marked the `File` field of the indicator module mandatory for the `File` type indicator
> **Note:** This change won't show up in SFSP upgrades. It's best to apply it manually to prevent the incorrect creation of file indicators.
- Added `Tenant` field of indicator module in *Record Uniqueness* settings

### War Rooms
- The war room module is marked as `Team Ownable` and `User Ownable`

### i18n changes
- Added *English* and *French* language support to all the modules comes OOB with SFSP
> **Note:** This change will only show up in FortiSOAR 7.5.0 onwards

## Playbook Enhancements

- The "Extract Indicators" playbook in the *03 - Enrich* playbooks collection now appends the indicators to the alert record

