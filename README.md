# 📊 Security Compliance Dashboard

An interactive, browser-based compliance tracking dashboard built for federal security assessment workflows. Visualizes control test results, open POA&M items, framework compliance status, and ATO timeline progress — all from a single self-contained HTML file powered by CSV data.

Built as part of a broader GRC portfolio: [github.com/RasanS-sudo](https://github.com/RasanS-sudo)

---

## What It Tracks

| Section | Description |
|---|---|
| **Framework Compliance** | Pass rates across NIST 800-53, FedRAMP, FISMA, FIPS 140-3, DoD SRG, ISO 27001 |
| **Control Test Results** | Per-control status (Pass / Fail / Review / N/A) with severity ratings |
| **Risk Heatmap** | Impact vs. likelihood matrix across finding categories |
| **Open POA&M Items** | Active plan of action items with remediation progress tracking |
| **ATO Timeline** | Milestone tracker from initial assessment through authorization decision |
| **KPI Counters** | Overall compliance %, open findings count, controls tested, days to ATO renewal |

---

## Files

```
compliance-dashboard/
├── dashboard.html          # Self-contained dashboard (open in any browser)
├── compliance_data.csv     # Control test results — one row per NIST 800-53 control
├── poam_data.csv           # Open POA&M items with status and remediation progress
└── README.md
```

---

## How to Use

**Option 1 — Local**
```bash
git clone https://github.com/RasanS-sudo/compliance-dashboard
cd compliance-dashboard
open dashboard.html   # macOS
# or just double-click dashboard.html in your file explorer
```

**Option 2 — GitHub Pages**

Push the repo and enable GitHub Pages from Settings → Pages → Deploy from branch `main`. The dashboard will be live at `https://RasanS-sudo.github.io/compliance-dashboard/dashboard.html`.

---

## CSV Structure

### `compliance_data.csv`

| Column | Description | Example |
|---|---|---|
| `control_id` | NIST 800-53 control identifier | `AC-2` |
| `control_name` | Control name | `Account Management` |
| `control_family` | Control family | `Access Control` |
| `framework` | Applicable framework | `NIST 800-53` |
| `result` | Test result | `PASS / FAIL / REVIEW / N/A` |
| `severity` | Finding severity | `HIGH / MEDIUM / LOW / N/A` |
| `tested_date` | Date control was tested | `2025-04-01` |
| `tester` | Name of assessor | `R. Salhi` |
| `notes` | Testing notes or finding details | Free text |

### `poam_data.csv`

| Column | Description | Example |
|---|---|---|
| `poam_id` | Unique POA&M identifier | `POAM-001` |
| `control_id` | Associated NIST control | `CM-6` |
| `finding_title` | Short description of the finding | `Baseline Config Deviation on 14 Nodes` |
| `risk_level` | Risk rating | `HIGH / MEDIUM / LOW` |
| `assigned_to` | Team responsible for remediation | `Security Team` |
| `open_date` | Date finding was opened | `2025-04-08` |
| `due_date` | Remediation due date | `2025-08-15` |
| `status` | Current status | `OVERDUE / IN PROGRESS / ON TRACK / CLOSED` |
| `remediation_progress_pct` | Percent complete | `35` |
| `description` | Full finding description | Free text |

---

## Why I Built This

GRC assessors working with NIST 800-53, FedRAMP, and FISMA spend a lot of time managing control evidence, tracking POA&M remediation, and reporting status to ISSOs and AOs. Most organizations use expensive tools like Archer, ServiceNow GRC, or spreadsheet-heavy manual processes.

This dashboard demonstrates how the same visibility can be delivered through clean data structures and a lightweight front-end — no licensing costs, no backend required, deployable anywhere. The CSV format mirrors how control data is typically exported from audit tools and SIEM platforms, making it straightforward to adapt to real assessment data.

---

## Skills Demonstrated

- NIST 800-53 Rev 5 control framework and family structure
- POA&M lifecycle management (open, track, close)
- ATO process stages: scoping → SSP → SAR → POA&M → authorization
- Data visualization for compliance reporting
- HTML/CSS/JS — self-contained single-file web app
- CSV data modeling for audit and assessment workflows

---

## Related Projects

- [GRC Compliance Toolkit](https://github.com/RasanS-sudo/grc-portfolio) — NIST control gap analyzer, RMF CLI tracker, FIPS 140-3 checker, ATO checklist
- [Python Security Toolkit](https://github.com/RasanS-sudo) — Port scanner and log analyzer

---

*Data in this repository is simulated for demonstration purposes only.*
