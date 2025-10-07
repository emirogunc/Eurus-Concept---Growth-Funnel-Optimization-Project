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

| Device  | LC-ROAS   | CAC (€) | Notes                   |
| ------- | --------- | ------- | ----------------------- |
| Desktop | 0.55–0.63 | 120–160 | Relatively efficient    |
| Mobile  | 0.47–0.49 | 150–165 | Slightly less efficient |
<img width="1024" height="1024" alt="ROAS" src="https://github.com/user-attachments/assets/652276ce-05b6-4e14-971f-c94a7c2cac5d" />

tep 3 — Incrementality via Geo-Holdout

Formulas applied:

	
𝑠
𝑐
𝑎
𝑙
𝑒
	
=
𝑠
𝑒
𝑠
𝑠
𝑖
𝑜
𝑛
𝑠
𝑡
𝑒
𝑠
𝑡
𝑠
𝑒
𝑠
𝑠
𝑖
𝑜
𝑛
𝑠
ℎ
𝑜
𝑙
𝑑
𝑜
𝑢
𝑡
		
	
𝑖
𝐶
𝑜
𝑛
𝑣
	
=
𝑝
𝑢
𝑟
𝑐
ℎ
𝑎
𝑠
𝑒
𝑠
𝑡
𝑒
𝑠
𝑡
−
𝑝
𝑢
𝑟
𝑐
ℎ
𝑎
𝑠
𝑒
𝑠
ℎ
𝑜
𝑙
𝑑
𝑜
𝑢
𝑡
×
𝑠
𝑐
𝑎
𝑙
𝑒
		
	
𝑖
𝑅
𝑒
𝑣
	
=
𝑟
𝑒
𝑣
𝑒
𝑛
𝑢
𝑒
𝑡
𝑒
𝑠
𝑡
−
𝑟
𝑒
𝑣
𝑒
𝑛
𝑢
𝑒
ℎ
𝑜
𝑙
𝑑
𝑜
𝑢
𝑡
×
𝑠
𝑐
𝑎
𝑙
𝑒
		
	
𝑖
𝐶
𝐴
𝐶
	
=
𝑠
𝑝
𝑒
𝑛
𝑑
𝑡
𝑒
𝑠
𝑡
𝑖
𝐶
𝑜
𝑛
𝑣
		
	
𝑖
𝑅
𝑂
𝐴
𝑆
	
=
𝑖
𝑅
𝑒
𝑣
𝑠
𝑝
𝑒
𝑛
𝑑
𝑡
𝑒
𝑠
𝑡
		
scale
iConv
iRev
iCAC
iROAS
	​

=
sessions
holdout
	​

sessions
test
	​

	​

=purchases
test
	​

−purchases
holdout
	​

×scale
=revenue
test
	​

−revenue
holdout
	​

×scale
=
iConv
spend
test
	​

	​

=
spend
test
	​

iRev
	​

	​



