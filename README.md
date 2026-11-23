# Consumer Credit Risk & Loan Default Intelligence Suite

[![Power BI](https://img.shields.io/badge/Power_BI-Desktop_Dashboard-F2C811?logo=powerbi&logoColor=black)](loan_risk.pbix)
[![Live Landing Page](https://img.shields.io/badge/GitHub_Pages-Live_Showcase-14B8A6?logo=github&logoColor=white)](https://ahmedelsayed7115.github.io/credit-risk-loan-analytics/)
[![Dataset](https://img.shields.io/badge/Dataset-601_Consumer_Loans-3F72AF)](merged_loan_data_fixed.csv)
[![Status](https://img.shields.io/badge/Status-Executive_Ready-success)]()

> **Live Interactive Landing Page:** [View on GitHub Pages](https://ahmedelsayed7115.github.io/credit-risk-loan-analytics/)  
> **Power BI Workbook:** [`loan_risk.pbix`](loan_risk.pbix)  
> **Scope:** 601 merged consumer loan originations (`borrower_profiles.csv` + `loan_applications.csv` $\rightarrow$ `merged_loan_data_fixed.csv`)  
> **Focus:** Credit score inflection boundaries, Debt-to-Income (DTI) leverage cliffs, ticket-size severity amplification, and a 9-box underwriting decision matrix

---

## Executive Summary

An end-to-end **Consumer Credit Risk & Underwriting Policy** analytics suite auditing **601 loan applications** with a **24.29% overall default rate (146 defaults)**. By linking relational borrower demographic profiles with loan application outcomes in Power BI, the analysis establishes empirical underwriting cutoffs across four risk dimensions:

1. **The FICO 700 Natural Risk Boundary (`4.2×` Default Multiplier):** Subprime borrowers (`520–599` credit score) default at **49.14% (57 / 116 loans)**—more than **4.2×** the super-prime `750+` tier (**11.69%, 27 / 231 loans**). Default risk drops sharply at the **700 FICO threshold** (from **28.00%** in `650–699` down to **16.28%** in `700–749`).
2. **The 40% Debt-to-Income (DTI) Leverage Cliff (`+10.8` pt Gap):** Defaulted borrowers carry an average DTI of **57.9%** versus **47.1%** for non-defaulted borrowers. Loans in the **20–40% DTI** band achieve the lowest default rate (**11.89%, 22 / 185**), whereas default rates jump to **27.55% (40–60% DTI)** and **36.05% (60%+ DTI)**.
3. **Loan Purpose & Ticket-Size Severity Amplification:** Discretionary **Wedding loans** record the highest default incidence (**32.14%, 18 / 56**), followed by **Home Improvement (28.57%)** and **Auto Loans (27.12%)**. In non-discretionary categories, defaulters borrow substantially larger principals than non-defaulters: **Education ($29,183 vs. $17,115, +70.5%)**, **Medical Expenses ($30,421 vs. $21,298, +42.8%)**, and **Debt Consolidation ($29,036 vs. $21,030, +38.1%)**.
4. **Early-Tenure Employment Risk (`< 2 Years` at `34.52%`):** Borrowers employed for **less than 2 years** default at **34.52% (29 / 84)**—nearly **2.0×** the rate of borrowers with **2–4 years** on the job (**17.54%, 20 / 114**), proving employment tenure is a much stronger risk discriminator than employment category (`Part-Time 27.69%` vs. `Full-Time 23.93%`).

---

## Executive KPI Scorecard (`n = 601` Loans)

| Risk Metric | Portfolio Value | Segment Breakdown | Policy Benchmark | Status |
| :--- | :---: | :--- | :---: | :---: |
| **Overall Portfolio Default Rate** | **24.29%** | `146` defaults / `601` total loans | `< 15.0%` Target | 🔴 Above Target |
| **Subprime (`520–599` FICO) Default Rate** | **49.14%** | `57 / 116` subprime loans defaulted | Decline / Secured Only | 🔴 Critical (`4.2×`) |
| **Prime (`700+` FICO) Default Rate** | **12.93%** | `41 / 317` loans (`16.3%` in 700–749; `11.7%` in 750+) | Standard Approval | 🟢 On Target |
| **Defaulted vs. Non-Defaulted Avg DTI** | **57.9% vs. 47.1%** | `+10.8` percentage-point leverage gap | `≤ 40%` Standard / `50%` Cap | 🟡 Inflection at 40% |
| **High-Leverage (`60%+` DTI) Default Rate** | **36.05%** | `62 / 172` loans (vs. `11.89%` in `20–40%` DTI) | Hard Decline Unsecured | 🔴 High Exposure |
| **Early-Tenure (`< 2 Yrs` Employed) Default** | **34.52%** | `29 / 84` loans (vs. `17.54%` at `2–4 yrs`) | Co-Signer / Reserve Req. | 🔴 2.0× Multiplier |

---

## Deep-Dive Risk Breakdowns

### 1. Credit Score Tier Performance
| Credit Score Range | Total Loans | Defaults | Default Rate | Portfolio Share | Risk Classification |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **520 – 599 (Subprime)** | 116 | **57** | **49.14%** | 19.3% | 🔴 Critical |
| **600 – 649 (Near-Prime)** | 93 | **27** | **29.03%** | 15.5% | 🟡 High |
| **650 – 699 (Near-Prime+)** | 75 | **21** | **28.00%** | 12.5% | 🟡 High |
| **700 – 749 (Prime)** | 86 | 14 | **16.28%** | 14.3% | 🟢 Moderate |
| **750+ (Super-Prime)** | 231 | 27 | **11.69%** | 38.4% | 🟢 Low |

### 2. Debt-to-Income (DTI) Ratio Segmentation
| DTI Range | Total Loans | Defaults | Default Rate | Underwriting Zone |
| :--- | :---: | :---: | :---: | :---: |
| **0 – 20% DTI** | 48 | 8 | **16.67%** | Low Leverage |
| **20 – 40% DTI** | 185 | 22 | **11.89%** | 🟢 Optimal Lending Zone |
| **40 – 60% DTI** | 196 | 54 | **27.55%** | 🟡 Conditional / Enhanced Review |
| **60%+ DTI** | 172 | **62** | **36.05%** | 🔴 Critical Leverage Zone |

### 3. Loan Purpose & Principal Amplification
| Loan Purpose | Loans | Defaults | Default Rate | Avg Ticket (All) | Avg Ticket (Default) | Avg Ticket (Non-Default) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Wedding** | 56 | 18 | **32.14%** | \$21,893 | \$21,006 | \$22,313 |
| **Home Improvement** | 70 | 20 | **28.57%** | \$23,407 | \$19,150 | \$25,110 |
| **Auto Loan** | 59 | 16 | **27.12%** | \$19,554 | **\$22,644** | \$18,405 |
| **Business Loan** | 58 | 14 | **24.14%** | \$21,014 | \$16,407 | \$22,480 |
| **Education** | 53 | 12 | **22.64%** | \$19,847 | **\$29,183** | \$17,115 |
| **Vacation** | 62 | 14 | **22.58%** | \$24,477 | \$24,307 | \$24,527 |
| **Major Purchase** | 68 | 15 | **22.06%** | \$23,165 | \$16,180 | \$25,142 |
| **Debt Consolidation** | 51 | 11 | **21.57%** | \$22,757 | **\$29,036** | \$21,030 |
| **Moving** | 56 | 12 | **21.43%** | \$21,300 | \$21,975 | \$21,116 |
| **Medical Expenses** | 68 | 14 | **20.59%** | \$23,176 | **\$30,421** | \$21,298 |

---

## Prioritized Underwriting Policy Recommendations

| Priority | Policy Rule | Target Segment | Expected Portfolio Impact |
| :---: | :--- | :--- | :--- |
| **P1 — Credit Floor** | **FICO 600 Minimum Floor for Unsecured Originations** | `520–599` FICO band (`116` loans, `49.1%` default) | Intercepts **57 of 146 total defaults (39.0%)**, cutting portfolio default rate from **24.3% to 18.4%** on remaining volume. |
| **P1 — DTI Cap** | **50% Hard DTI Ceiling & 40% Conditional Threshold** | `60%+` DTI band (`172` loans, `36.0%` default) | Eliminates extreme leverage originations where default rates triple relative to the `20–40%` safe zone (`11.9%`). |
| **P2 — Ticket Cap** | **\$22,000 Principal Cap on Education, Medical & Consolidation** | High-ticket requests (`$29K–$30.4K` default avg) | Curbs the `+38%` to `+71%` ticket-size severity spike driving losses in non-discretionary loan categories. |
| **P2 — Tenure Gate** | **Co-Signer / Reserve Mandate for `< 2 Years` Employment** | `< 2 yrs` tenure (`84` loans, `34.5%` default) | Mitigates the `2.0×` early-tenure default hazard compared to borrowers with `2–4 years` stability (`17.5%`). |
| **P3 — Pricing** | **Risk-Adjusted Rate Premiums on Discretionary Purposes** | Wedding (`32.1%`) & Part-Time (`27.7%`) segments | Aligns APR risk premiums and stricter `< 40%` DTI caps with elevated category default frequency. |

---

## Repository Structure & How to Run

```text
credit-risk-loan-analytics/
├── README.md                     # Executive case study & underwriting policy report
├── index.html                    # Interactive dark-mode GitHub Pages showcase (Chart.js)
├── loan_risk.pbix                # Interactive Power BI Desktop dashboard
├── merged_loan_data_fixed.csv    # Cleaned & merged master analytical dataset (601 loans)
├── borrower_profiles.csv         # Raw borrower demographic & credit attributes
├── loan_applications.csv         # Raw loan application & default outcome records
└── loan_risk_report.html         # Tabular audit report snapshot
```

1. **Clone the repository:**
   ```bash
   git clone https://github.com/ahmedelsayed7115/credit-risk-loan-analytics.git
   cd credit-risk-loan-analytics
   ```
2. **Open `loan_risk.pbix`** in **Microsoft Power BI Desktop** to explore interactive cross-filtering across credit tiers, DTI bands, loan purposes, and employment profiles, or view the live web dashboard at **[ahmedelsayed7115.github.io/credit-risk-loan-analytics](https://ahmedelsayed7115.github.io/credit-risk-loan-analytics/)**.
