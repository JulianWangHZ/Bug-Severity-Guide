# 🐞 Bug Severity Guide (A/B/C) & Priority (P0–P4)

[English](README.md) | [中文](README_zh.md)

A concise, practical guide for classifying product defects.  
In addition to **Priority (P0–P4)**—which determines *when* we fix an issue—we also use **Severity (A/B/C)** to express the defect’s *impact on users and the system*. Using both helps the team triage quickly and consistently.

---

## 📚 Table of Contents
- [📘 Why Severity and Priority?](#why-severity-and-priority)
- [🧭 Definitions at a Glance](#definitions-at-a-glance)
- [🧱 Severity Levels](#severity-levels)
  - [🔴 A — Critical](#-a--critical)
  - [🟡 B — Serious](#-b--serious)
  - [🔵 C — Non-critical](#-c--non-critical)
- [🗺️ How Severity Maps to Priority](#how-severity-maps-to-priority)
- [🧪 How to Choose Quickly (Rubric)](#how-to-choose-quickly-rubric)

---

## 📘  Why Severity and Priority?

- **Severity = Impact** (how bad the problem is for users/system)  
- **Priority = Urgency** (how soon we should fix it)

> In practice, we use both: high-severity issues *tend* to receive higher priority, but not always (e.g., a severe bug in a rarely used, temporarily disabled feature might not be P0).

---

## 🧭  Definitions at a Glance

- **Severity (A/B/C):** Ranges from system-level failures and security risks (**A**) to visual/wording issues (**C**).
- **Priority (P0–P4):** Scheduling lever from “fix immediately” (**P0**) to “nice to have” (**P4**).

---

## 🧱 Severity Levels

### 🔴 A — Critical
Severe, system-level impact or security risk. Requires immediate attention to avoid major business impact.

**Definition**
- Severely disrupts normal product use
- Causes support escalations or **security** exposure
- Must be fixed immediately

**Examples**
- Authentication bypass allows entry without valid credentials
- Payment completes but **is not recorded**, creating financial risk
- API responds with **sensitive personal data** (e.g., credit card data leakage)
- System **crashes under sustained load**, blocking all users

---

### 🟡 B — Serious
Functional deviations that disrupt key workflows but have workarounds; notable performance degradations.

**Definition**
- Feature does not behave as expected
- Affects primary business flows; workaround or manual steps exist
- Includes **performance issues** impacting user experience

**Examples**
- Filters apply but results are **incorrect**, forcing manual verification
- Reservation list takes **>20 seconds** to load, delaying operations
- Branch management page shows **incorrect info** until refresh
- Export occasionally fails and requires **multiple retries**

---

### 🔵 C — Non-critical
UI or wording issues that do not affect core functionality or business decisions.

**Definition**
- Localized UI or copy inconsistencies
- Does **not** impact core function or cause misinterpretation
- Optimization-level; can be scheduled later

**Examples**
- “Submitting…” label persists briefly though the action succeeded
- Typo in modal title: “**Confim**” instead of “Confirm”
- Card color/style deviates from design spec
- Long branch names **truncate** visually but remain clickable

---

## 🗺️ How Severity Maps to Priority

> This table shows **common** pairings. Product/engineering may adjust based on context, release stage, customer commitments, and risk.

| **Severity** | **Definition**                                                         | **Typical Priority** | **Examples**                                  |
| --- | --- | --- | --- |
| 🔴 A (Critical) | System-breaking, security, or data integrity issues                   | **P0 / P1**          | System crashes, payment loss, security holes  |
| 🟡 B (Serious)  | Major functional deviation or performance degradation with workaround | **P1 / P2**          | Wrong filter results, slow loads, export flakiness |
| 🔵 C (Non-critical) | UI/copy defects; no functional impact                             | **P3 / P4**          | Typos, style mismatches, truncated text       |

---

## 🧪 How to Choose Quickly (Rubric)

- **Does it block all users or expose data/security?** → **Severity A**
- **Does it break a key flow but has a viable workaround?** → **Severity B**
- **Is functionally OK but visually or copy-wise off?** → **Severity C**

When uncertain, **escalate one level** during triage and adjust after impact verification.

---
