# Growth Analytics Case: Eurus Concept  

This repository is a **synthetic growth case study** for *Eurus Concept*, built with **GA4, GTM, Hotjar, Looker Studio, and Zapier/Make**.  
It demonstrates how to run a growth diagnostic, design experiments, and visualize impact in a structured workflow.  

---

## Contents  
- **exp001_looker.png** → Funnel & CAC/ROAS dashboard from Looker Studio  ![Eurus-Concept---Growth-Funnel-Optimization-Project](/EXP1/Eurus_Looker_.pdf)
- **hotjar_report_exp001.pdf** → Heatmap & behavior insights (synthetic Hotjar analysis)  ![Eurus-Concept---Growth-Funnel-Optimization-Project](exp002_hotjar_report.pdf)
- **gtm_report_exp001.md** → Event tracking audit & recommendations (synthetic GTM report)   ![Eurus-Concept---Growth-Funnel-Optimization-Project](exp003_gtm_report.pdf)

---

## Methodology  

1. **Acquisition Diagnostic**  
   - Metrics: CAC, ROAS, ARPU
   - Methods: Incrementality test (geo-holdout), attribution model comparison  

2. **Funnel Diagnostic**  
   - Funnel: Session → Signup → Activation → Purchase  
   - Metrics: Signup CR, Activation CR, Purchase CR  
   - Guardrails: Bounce rate, latency, churn  

3. **Behavioral Insights**  
   - Hotjar heatmaps → Identified checkout friction (shipping fee bottleneck)  
   - Survey triggers → 25% complain about “unexpected fees”  

4. **Tracking Audit**  
   - GTM setup checked for missing events (checkout_error, kyc_fail)  
 

---

## Key Findings  

- **Bottleneck** → Activation to Purchase step (shipping fee friction).  
- **Channel efficiency** → TikTok Mobile had lower CAC vs Meta Mobile.  
- **Seasonality** → Revenue spikes early in the month (promotion impact).  

---

## Tools Used  
- **GA4** → Traffic & conversion metrics  
- **GTM** → Event tracking & attribution  
- **Hotjar** → Heatmap & session recordings  
- **Looker Studio** → Funnel dashboards & anomaly detection  
- **Zapier/Make** → Workflow automation (alerts, reporting)  
- **GitHub** → Repository for synthetic case study  

---
