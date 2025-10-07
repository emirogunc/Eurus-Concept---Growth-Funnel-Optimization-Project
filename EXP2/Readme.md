# EXP-002: Paid Search Incrementality vs Platform ROAS  
Dataset: ![Eurus-Concept---Growth-Funnel-Optimization-Project](eurus_exp_bible_weekly.csv)

---

## Experiment Context  

**Hypothesis:**  
Paid Search campaigns show strong *last-click ROAS* on platform dashboards — yet actual incrementality (via geo-holdout) may be weak.  
Goal: validate true incremental ROI and reallocate spend accordingly.

| Objective | Metric | Method |
|------------|---------|--------|
| Evaluate true Paid Search impact | iROAS (Incremental ROAS) | Geo-Holdout test |
| Compare with platform metrics | Last-Click ROAS vs Incremental | Same 8-week window |
| Optimize budget allocation | Incremental-based reallocation | iROAS weighting |

---

## 2️⃣ Data Overview  

**File:** ![Eurus-Concept---Growth-Funnel-Optimization-Project](eurus_exp_bible_weekly.csv)

**Period:** 2023-10 → 2025-09  
**Type:** Syhentetic

| Column | Example | Description |
|---------|----------|-------------|
| `week_start` | 2025-08-11 | Week start date |
| `geo` | NL-ZH | Region (Geo) |
| `channel` | Paid Search | Marketing channel |
| `device` | Mobile/Desktop | Device type |
| `purchases`, `revenue`, `spend` | numeric | Funnel metrics |
| `holdout_flag` | 0 / 1 | 0=test, 1=holdout |

---

## Step-by-Step Analysis  

### Step 1 — Last-Click Performance (Last 8 Weeks)

![Eurus-Concept---Growth-Funnel-Optimization-Project](Paid_Search___Last_8_Weeks_by_Device___Channel__LC_ROAS__CAC_.csv)

| Device  | LC-ROAS   | CAC (€) | Notes                   |
| ------- | --------- | ------- | ----------------------- |
| Desktop | 0.55–0.63 | 120–160 | Relatively efficient    |
| Mobile  | 0.47–0.49 | 150–165 | Slightly less efficient |
<img width="512" height="512" alt="ROAS" src="https://github.com/user-attachments/assets/652276ce-05b6-4e14-971f-c94a7c2cac5d" />

Step 3 — Incrementality via Geo-Holdout

Formulas applied:

Scale= Session(test)/Session(Holdout)

iConv= Purchase(t)-Purchase(h)xscale

iRev= Revenue(t)-Revenue(h)xscale

iCAC= Spend(t)/iConv

iROAS= iREV/Spenc(t)

GEO-Level Results:

| Geo    | iROAS     | iConv | iRev (€) | Comment                     |
| ------ | --------- | ----- | -------- | --------------------------- |
| BE-BRU | -0.12     | -9.1  | -652     | Negative incremental impact |
| LU-LUX | -0.11     | -4.6  | -471     | Negative                    |
| NL-ZH  | **+0.13** | +11   | +719     | Positive, scalable          |
| NL-NH  | n/a       | —     | —        | Missing holdout data        |

Step 4 — Budget Reallocation Simulation
​
| Geo    | Old Spend (€) | iROAS | Suggested New Spend (€) | Δ       |
| ------ | ------------- | ----- | ----------------------- | ------- |
| BE-BRU | 5,352         | -0.12 | 0                       | ↓ -5.3k |
| LU-LUX | 4,249         | -0.11 | 0                       | ↓ -4.2k |
| NL-ZH  | 5,531         | +0.13 | **14,600**              | ↑ +9.1k |
| NL-NH  | 8,023         | n/a   | **8,400**               | ≈ same  |

Result:
Reallocating 23k€ total spend purely to positive-incremental geos raises overall iROAS ≈ +25%, even if total spend stays flat.

Guardrails & Governance:

| Guardrail          | Limit           | Purpose                    |
| ------------------ | --------------- | -------------------------- |
| Spend drop per geo | ≤ 70 %          | Avoid sharp traffic loss   |
| iROAS < 0          | Cut 80 % budget | Stop negative ROI          |
| iROAS > 0.5        | +30 % boost     | Scale winning geos         |
| Evaluation window  | 4–6 weeks       | Seasonal smoothing         |
| Metrics of truth   | iRev, iConv     | Ignore platform ROAS noise |


Summary

Findings:

Paid Search looked healthy via last-click, yet only ~30 % of spend was truly incremental.

NL-ZH drives real lift; BE-BRU & LU-LUX are wasted budget.

Next Step:

Run another 4-week geo-holdout validation after redistribution.

Monitor incremental conversions vs spend in Looker Studio dashboard.



