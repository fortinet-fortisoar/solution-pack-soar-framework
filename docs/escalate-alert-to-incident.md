| [Home](../README.md) |
|:---------------------|

## Automating Alert to Case Escalation

### Overview

In a high-volume SOC environment, manual triage is a bottleneck. The **Escalation Rules** module provides an automated *filtering and linking* layer. It ensures that repetitive alerts are consolidated and that related events&mdash;such as a single brute-force attack targeting multiple assets&mdash;are unified under a single **Case** record.

---

### Understanding the Escalation Logic

The system follows a four-step lifecycle to process every alert. This automation is designed to ease the burden on SOC analysts by pre-correlating data before it reaches the case queue.

1. **Extracting Indicators:** When an alert is ingested, the system extracts key artifacts (IPs, Hostnames, URLs). Once complete, the alert state moves to *Indicator Extracted*.
2. **Rule Matching:** The **Rule Engine Service** compares the alert against active **Escalation Rules**.
    - **Tie-breaking:** If an alert matches multiple rules, the system selects the rule with the **highest Priority** (`P0` > `P1` > `P2`). If priorities are equal, it uses the **latest** created rule.
3. **Correlation & Grouping:** The engine looks back **28 days (Default)** to find similar alerts based on the **Group By** fields (for example, matching the same Source IP).
4. **Escalation vs. Linking:** 
    - If no similar case exists, a **new Case** is created.
    - If a similar case or escalated alert is found, the new alert is **linked** to the existing record instead of creating a duplicate.
    - **Manual Override:** If an analyst has already manually escalated an alert, the automation is smart enough to detect the existing case and link new matching alerts to it automatically.

---

### The Escalation Rules Module

Administrators and Analysts can create rules to handle specific attack patterns. Each rule is a record within the **Escalation Rules** module.

#### Key Configuration Fields

| Field                    | Description                                                                                                               |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------|
| **Escalation Criteria**  | A JSON field defining the matching logic (for example, `Event Type = Brute Force`).                                       |
| **Rule Configuration**   | A filter builder where you select any Alert field, an operator (`=`, `!=`, `>`, etc.), and a **static** comparison value. |
| **Group By**             | Defines the "binding" fields for correlation (for example, `hostname` and `hostIP`).                                      |
| **Target Case Name** | The static name assigned to the resulting case.                                                                       |
| **Target Case Type** | A dropdown using the standard `picklist.caseType` (for example, Malware, Phishing).                                   |
| **Activation Limit**     | The number of linked alerts required before the Case is marked "Active" for analyst review.                           |
| **System**               | If enabled, this is a pre-defined rule that cannot be modified by users.                                                  |

---

### 3. Automated Reconciliation

To prevent "race conditions" where two identical alerts arrive at the exact same millisecond, the framework utilizes a **Reconciliation Playbook**.

- **Schedule:** Runs every **5 minutes (Default)**.
- **Action:** It scans for alerts that have linked records but were not themselves escalated.
- **Logic:** It identifies the "Primary Alert" (the one with the lowest ID) and ensures all related alerts are correctly mapped to that primary alert's case. It also checks if the **Activation Limit** has been met, to set the Case status to `active`.

---

### 4. Summary of Constraints

- **Look-back Period:** Rules only consider similar alerts/cases created within the last **28 days (Default)**. Alerts older than this will trigger a fresh escalation.
- **Precedence:** Higher priority (P0) rules overrides lower priority ones; with creation time being the tie-breaker.


