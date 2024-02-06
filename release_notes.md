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

### Indicators

- Marked the `File` field of indicator module mandatory for the `File` type indicator
> **Note:** This change won't show up in SFSP upgrades. It's best to apply it manually to prevent incorrect creation of file indicators.
- Added `Tenant` field of indicator module in *Record Uniqueness* settings

## Playbook Enhancements

- The "Extract Indicators" playbook in the *03 - Enrich* playbooks collection now appends the indicators to the alert record