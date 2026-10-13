# Marketing Forecasting & Budget Optimization

An end-to-end marketing analytics portfolio case study using synthetic dental-services marketing data. The project explores funnel performance, channel efficiency, forecast validation, and budget allocation scenarios.

## Interactive dashboard
Once GitHub Pages is enabled, open the [live dashboard](https://gtejareddy-45.github.io/marketing-forecasting-budget-optimization/). The [HTML source](./index.html) is also available in this repository.

The charts use Chart.js from a CDN, so an internet connection is required for the chart visuals.

## Key results in the synthetic dataset
- Media spend: approximately **$9.85M** across January 2023–December 2025
- Attributed revenue: approximately **$22.00M**
- Blended ROAS: approximately **2.23×**
- Leads: **133,251**; completed visits: **33,338**
- Google Search had the strongest historical ROAS among the four included channels (**3.25×**).

## Repository contents
- `index.html` — interactive executive dashboard preview
- `data/monthly_totals.csv` — 36 monthly aggregate records
- `data/channel_performance.csv` — channel-level KPI summary
- `data/office_performance.csv` — office-level KPI summary
- `data/budget_scenarios.csv` and `data/budget_allocation.csv` — modeled scenario results
- `data/forecast_evaluation.csv` — holdout model error comparisons
- `data/experiment_summary.csv`, `data/group_comparison.csv`, `data/market_experiment.csv` — descriptive incrementality-practice outputs
- `powerbi/measures.dax` — DAX starter measures for the published summary tables
- `powerbi/marketing_theme.json` — optional Power BI report theme
- `powerbi/BUILD_GUIDE.md` — step-by-step report assembly guide

## Power BI
The repository provides CSVs, starter DAX, a theme, and report-building instructions. A native `.pbix` file has not been created here; assemble the report in Power BI Desktop using the steps in [the build guide](./powerbi/BUILD_GUIDE.md).

## Important limitations
- All data are **synthetic** and are for portfolio practice only; they are not actual company or patient data.
- Forecast and budget outputs are modeled scenarios, not causal findings or guaranteed business outcomes.
- Treatment and control markets were fixed by group, and a pre-period baseline is not included. The experiment comparison is descriptive and should not be presented as proof of causal lift.
- Summary tables are pre-aggregated at different grains. **Do not relate all summary tables together blindly**, as doing so can double-count metrics.
