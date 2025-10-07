# EXP-002: Paid Search Incrementality vs Platform ROAS  
Dataset: `/eurus_exp_bible_weekly.csv`

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

**File:** `eurus_exp_bible_weekly (1).csv`  
**Period:** 2023-10 → 2025-09  
**Rows:** 5,880 | **Columns:** 21  

| Column | Example | Description |
|---------|----------|-------------|
| `week_start` | 2025-08-11 | Week start date |
| `geo` | NL-ZH | Region (Geo) |
| `channel` | Paid Search | Marketing channel |
| `device` | Mobile/Desktop | Device type |
| `purchases`, `revenue`, `spend` | numeric | Funnel metrics |
| `holdout_flag` | 0 / 1 | 0=test, 1=holdout |

---

## 3️⃣ Step-by-Step Analysis  

### 🧩 Step 1 — Data Audit  
- Verified structure, separators, and column integrity.  
- Confirmed weekly granularity and holdout flags.  

```python
df.columns
['week_start','geo','device','channel','purchases','revenue','spend','holdout_flag', ...]
