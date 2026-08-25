# 🥚Egg Farm Business — Data Platform

> A full-stack data portfolio project built around the exhaustive and systematic simulation of a commercial laying hen farm — developed by a Veterinary Doctor, in parallel with a Master of Science in Predictive and Integrative Biology and a PhD in animal science, and designed to become the operational live management system of a real farm post-PhD.

---

## What This Project Is

This repository is the data infrastructure for a **simulated then real** egg production business in Morocco.

The core idea is simple: most poultry producers figure out their data systems _after_ launch, under pressure, with real money at risk. This project inverts that. By building the entire analytical platform — production tracking, financial modelling, feed optimisation, market intelligence — during the academic years, the learning curve is behind the business before it opens, not ahead of it.

The project has three overlapping lives:

|Layer|Description|Timeline|
|---|---|---|
|**Shadow business**|Full simulation of a Moroccan laying hen operation|MSc + PhD years|
|**Data portfolio**|Public proof of domain expertise and technical skills|MSc + PhD years|
|**Live system**|Real farm analytics platform, post-launch|After PhD|

---

## Why This Project Exists

The author is currently based in Morocco and pursuing an MSc followed by a PhD in animal science (poultry nutrition / production systems). The long-term goal is to launch a commercial laying hen operation in Morocco after completing the doctorate.

The academic trajectory — coursework in nutrition, production efficiency, flock management, and statistical modelling — maps directly onto the analytical problems a poultry business needs to solve. This project is where that knowledge gets translated into a working data system.

The simulation is built around Morocco's actual market conditions: MAD-denominated financials, ONICL wholesale price data, Ramadan demand seasonality, local feed ingredient availability, and the regulatory environment (ONSSA). The Morocco context is not decoration — it is load-bearing.

---

## Who This Is For

**Recruiters and hiring managers** looking for evidence of applied data skills in a domain where domain knowledge and technical skills rarely overlap. The models here are grounded in real agricultural science (Wood's production curve, least-cost linear programming formulations, FCR analysis), not toy datasets.

**Academic collaborators and supervisors** who want to see research outputs translated into operational tools. Several models in this project are being designed to integrate real farm data collected during doctoral fieldwork.

**Future investors or lenders** for the farm itself. The financial model — break-even analysis, cash flow projection, payback period — will serve as the quantitative backbone of the business plan.

---

## What's Inside (High-Level)

The full technical specification lives in [`farm_simulation_plan.md`](https://claude.ai/chat/farm_simulation_plan.md). Here is the overview:

### Data Infrastructure

- PostgreSQL relational database with a fully normalised schema (flocks, feed, health events, egg sales, costs, market prices)
- R-based ETL pipeline ingesting from FAOSTAT, ONICL, ITAVI benchmarks, and local price feeds
- Synthetic data generation for the simulation phase; designed to accept real farm data without schema changes

### Analytics & Modelling

- **Production curve modelling** — Wood's model fitted to weekly lay rate data; actual vs breed-standard deviation analysis
- **Feed cost analysis** — FCR tracking, least-cost formulation (linear programming with `lpSolve`), phase feeding simulation
- **Financial model** — monthly cash flow, break-even egg price, working capital requirements, ROI, payback period
- **Predictive models** — mortality risk (logistic regression → random forest), cull timing optimisation, feed price forecasting (Prophet)
- **Market intelligence** — Moroccan wholesale price seasonality, Ramadan demand surge modelling, margin analysis by sales channel

### Dashboards & Reporting

- Power BI flock performance dashboard
- Power BI financial dashboard
- Automated weekly flock report (R Markdown → PDF)
- Market intelligence dashboard

---

## Tech Stack

|Layer|Tools|
|---|---|
|Database|PostgreSQL|
|Data processing & modelling|R (tidyverse, ggplot2, lubridate, lpSolve, Prophet)|
|Dashboards|Power BI|
|Automated reporting|R Markdown|
|Version control|Git / GitHub|
|Environment|Docker (local), `.env`-managed credentials|

---

## Repository Structure

```
morocco-egg-farm/
│
├── README.md
├── farm_simulation_plan.md     ← Full farm blueprint and technical spec
├── .env.example
├── requirements.txt
├── docker-compose.yml
│
├── data/
│   ├── raw/
│   ├── processed/
│   ├── synthetic/
│   └── external/               ← FAOSTAT, ONICL, ITAVI, feed prices
│
├── database/
│   ├── schema.sql
│   ├── seed_data.sql
│   └── erd.png
│
├── etl/                        ← Ingest, transform, load scripts (R)
├── analytics/                  ← KPIs, cost analysis, financial model
├── models/                     ← Production curve, mortality, FCR, price forecasting
└── dashboards/                 ← Power BI files and R Markdown reports
```

---

## Project Status

This project is being built incrementally across the MSc and PhD years. Commits are intentionally spread over time — the timeline of the repository is part of the story.

|Phase|Status|
|---|---|
|Phase 0 — Foundation (SQL, schema, farm definition)|🔄 In progress|
|Phase 1 — MSc year (ETL, KPIs, first models, dashboards)|⏳ Upcoming|
|Phase 2 — PhD years (real data integration, optimisation tools)|⏳ Upcoming|
|Phase 3 — Pre-launch validation|⏳ Upcoming|

---

## Notes on Language

Code comments and documentation are in English to maximise international visibility. The README is bilingual (English + French) for relevance in the Moroccan and French academic contexts. Dashboard labels in the live business version will be in French or Arabic.

---




