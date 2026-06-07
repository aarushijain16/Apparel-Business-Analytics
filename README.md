# End-to-End Apparel Business Analytics
### Demand Forecasting · Inventory Optimisation · Working Capital Analysis
### SQL (PostgreSQL) · Python · Power BI · Holt-Winters · SARIMA

---

## Overview

This project builds a full-stack analytics system for a B2B apparel 
manufacturer - modelled on synthetic data that replicates the actual 
demand patterns, SKU variability, distributor payment cycles, and 
seasonal production rhythms of a real business.

The system integrates SQL, Python, and Power BI to convert raw 
transactional data into commercial decisions across demand planning, 
inventory management, working capital optimisation, and production alignment.

**Tools:** PostgreSQL · Python (Pandas, NumPy, Statsmodels) · 
Power BI · Holt-Winters · SARIMA · DAX

---

## Business Context

This project was built on synthetic data modelled on the real business 
operations of a B2B apparel manufacturer - replicating actual demand 
patterns, SKU variability, distributor payment cycles, and seasonal 
production rhythms.

The business problems it addresses are real:

- No visibility into top-performing products or revenue-driving SKUs
- Production planned reactively - not aligned with demand cycles
- ~$60M working capital locked in distributor receivables (avg DSO ~177 days)
- Demand forecasting done manually with no statistical models in place
- Inventory planning inefficient - overstock in low seasons, 
  stockouts in peak periods

---

## Analytical Approach

**SQL-Based Business Analysis**
- Price band profitability analysis
- Top-performing SKU identification and margin ranking
- Working capital simulation via DSO impact modelling
- Distributor payment behaviour segmentation

**Power BI Dashboards (Connected to PostgreSQL)**
Four live dashboards built for commercial and ops teams:
- Sales Overview
- Distributor Performance
- Product Analytics
- Production Monitoring

**Time Series Forecasting (Python)**

| Model | Description | MAPE |
|---|---|---|
| SARIMA | Trend + seasonality + AR components | 4.91% |
| **Holt-Winters** | **Exponential smoothing + seasonality** | **3.09% ✓** |

Holt-Winters selected as final model - lower MAPE and better 
handling of seasonal volatility in apparel demand cycles.

**12-Month Demand Forecast**
- Captures seasonality, trend, and volatility
- Provides production planning anchor 2–3 months ahead of peak seasons

---

## Key Findings

**~$60M potential working capital opportunity**
SQL-based DSO simulation revealed average debtor days of ~177 days 
had tied up approximately $60M in working capital. A subset of 
chronic late-paying distributors accounted for the majority of 
the exposure - a concentrated, addressable risk.

*Note: This is a modelled estimate based on synthetic data 
replicating real apparel business dynamics.*

**~11.7% demand-supply gap**
Power BI production monitoring revealed consistent 11.7% 
underproduction relative to actual demand - meaning the business 
was structurally losing ~12% of addressable revenue due to 
misaligned production planning, not demand weakness.

**Mid-price segments ($240–$480) drive maximum revenue**
Price band profitability analysis showed mid-tier SKUs generated 
the highest revenue concentration. Premium segments had lower 
volume; entry-level had lower margins. The mid-tier was the 
optimal zone - underinvested relative to its contribution.

**Demand is seasonal but highly predictable**
Time series decomposition confirmed strong recurring seasonality. 
Holt-Winters captured these patterns with 3.09% MAPE - meaning 
12-month forward demand forecasts are reliable enough to anchor 
production and inventory decisions.

**SKU revenue is heavily concentrated**
Pareto analysis showed revenue concentrated in a small number of 
top-performing designs. A large tail of SKUs contributed minimal 
revenue while consuming inventory capital - a clear 
rationalisation opportunity.

---

## Business Recommendations

**Implement forecast-led production planning**
Use Holt-Winters demand forecasts to set monthly production targets 
2–3 months ahead of peak seasons. Expected impact: reduced stockouts, 
improved capacity utilisation, lower lost-sales rate.

**Release $60M+ working capital via distributor segmentation**
Segment distributors by payment risk. Apply stricter credit terms 
to chronic late payers, incentivise early payments with cash 
discounts, adjust credit limits based on payment history.

**Prioritise mid-price SKUs ($240–$480)**
Reallocate production capacity and marketing investment toward 
the highest revenue-density segment. This is a capital allocation 
decision backed by price band profitability data.

**Phase out non-performing SKUs**
Rationalise the long tail of low-revenue, low-margin SKUs to free 
inventory capital. Introduce a data-backed product launch framework 
so new SKUs are evaluated against demand and margin thresholds 
before entering production.

**Build a monthly demand vs production review dashboard**
Deploy a live Power BI dashboard tracking forecast vs actual demand 
with alerts for major deviations - shifting decision-making from 
reactive to proactive.

---

## Strategic Insight

The business does not suffer from unpredictable demand.
 It suffers from poor alignment between predictable demand and operational decisions.
 The opportunity is not in the data - it is in the decisions the data enables.

---

## Project Structure
```
Apparel-Business-Analytics/
│
├── README.md
├── data_dictionary.md
├── sql/              -> Price band, DSO simulation, SKU ranking queries
├── notebook/         -> Python forecasting models (SARIMA, Holt-Winters)
├── dashboards/       -> Power BI .pbix files
├── data/             -> Synthetic dataset
└── images/           -> Visualisations and dashboard screenshots
```
---

## Tools & Technologies

| Tool | Usage |
|---|---|
| PostgreSQL | Price band analysis, DSO simulation, SKU ranking |
| Python (Pandas, NumPy, Statsmodels) | EDA, time series forecasting |
| Holt-Winters | Final demand forecasting model (MAPE: 3.09%) |
| SARIMA | Benchmark model (MAPE: 4.91%) |
| Power BI + DAX | Four live dashboards connected to PostgreSQL |

---

## Dataset Note

This project uses synthetic data built to replicate the operational 
reality of a real B2B apparel manufacturer - including demand 
patterns, SKU variability, distributor payment behaviour, and 
seasonal production cycles. Financial impacts are modelled estimates, 
not real business outcomes.

---

*Part of the E-Commerce & Supply Chain Analytics Portfolio*
*[View full portfolio](https://aarushijportfolio.lovable.app/)*
