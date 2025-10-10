## Eurus Paid Acquisition Automations

This repository documents two Make.com (Integromat) automations built for Eurus Concept to demonstrate no-code marketing data workflows using synthetic ad reports instead of live Google/Meta/TikTok APIs.

# 1. Paid Reporting Automation

Goal:
Automatically collect daily paid-media metrics and send a unified summary to Google Sheets and Slack.

How it works:

A synthetic CSV dataset ![Eurus-Concept---Growth-Funnel-Optimization-Project](/Eurus-Concept---Growth-Funnel-Optimization-Project) simulates daily spend, clicks, revenue, and ROAS for three channels: Meta, TikTok, and Google Search.

Make parses the JSON or CSV, iterates through each channel, and appends the data to a Google Sheet (Eurus Paid Report).

A final Slack message summarizes daily performance with spend, revenue, and ROAS.

Purpose:
Removes manual reporting work and provides instant visibility for the team each morning.

------

2. ROAS Drift Guard

Goal:
Detect underperforming campaigns and send automatic Slack alerts when metrics fall below thresholds.

How it works:

Each morning, Make reads the latest data from the Google Sheet.

It checks for anomalies where ROAS < 1.5, CTR < 0.01, or Spend > 500.

If any condition is true, a Slack alert is triggered with channel-level details.

Purpose:
Acts as an early-warning system for paid campaigns, ensuring performance issues are caught immediately.


------


Summary

Both automations are designed as reusable, no-code templates showing how Eurus can:

Prototype reporting pipelines without needing API access

Combine data flow (Sheets) and communication (Slack)

Build scalable marketing analytics in Make using synthetic data

Tech stack: Make.com, Google Sheets, Slack
Dataset: /data/eurus_paid_reporting_auto.csv (synthetic sample)
License: MIT
