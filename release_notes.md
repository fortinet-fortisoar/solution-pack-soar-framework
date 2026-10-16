| [Home](./README.md) |
|---------------------|

# Release notes

The following table lists the FortiSOAR versions compatible with this release.

| Compatible Version         |
|----------------------------|
| FortiSOAR v8.0.1 and later |

## What's new

This release includes the following enhancements.

### Renamed dashboards

The following dashboards are renamed.

| Previous Name | Updated Name        |
|---------------|---------------------|
| Overview      | SOC Operations KPIs |
| Analyst       | SOC Analysts        |
| ROI Summary   | SOC ROI Summary     |

### Reports in system time zone

The following reports now show timings in the system time zone:

- Case Summary Report
- Overdue Alerts Activities
- Overdue Cases Activities
- Unhandled Activities
- War Room Summary Report
- Weekly Alert Report
- Weekly Case Report
- Weekly IOC Report

### Filename indicator support in hunt playbooks

The following playbooks in the `05 - Hunt` collection now support the **Filename** indicator type:

- Hunt (On Create) - Initiate IOC Hunt
- Hunt Indicators (Type All)
- Indicator (Manual Trigger) - Initiate IOC Hunt

## Fixed issues

This release fixes the following issue.

### URL extraction retains a trailing backslash

URL indicator extraction no longer retains a backslash at the end of a URL. Fresh installs of v4.1.0 include the corrected regex. If you upgrade from an earlier version, or use FortiSOAR 8.0.0 with an earlier SOAR Framework version, update the regex manually. For more information, see [Updating the URL extraction regex](./docs/upgrading-sfsp-to-latest.md#updating-the-url-extraction-regex).