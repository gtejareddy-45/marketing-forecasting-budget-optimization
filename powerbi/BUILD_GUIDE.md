# Power BI report build guide

This repository includes pre-aggregated CSV summaries, DAX starter measures, and an optional theme file. You can build a working Power BI report without Tableau.

## 1. Import the data
Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/). In Power BI Desktop, use **Home → Get data → Text/CSV** and import the following files from the cloned/downloaded repository:

- `data/monthly_totals.csv` → rename the table to **Monthly Totals**
- `data/channel_performance.csv` → rename the table to **Channel Performance**
- `data/office_performance.csv` → rename the table to **Office Performance**
- `data/budget_scenarios.csv` → rename the table to **Budget Scenarios**
- `data/budget_allocation.csv` → rename the table to **Budget Allocation**
- `data/forecast_evaluation.csv` → rename the table to **Forecast Evaluation**
- `data/experiment_summary.csv` → rename the table to **Experiment Summary**
- `data/market_experiment.csv` → rename the table to **Market Experiment**
- `data/group_comparison.csv` → rename the table to **Group Comparison**

For each table, select **Transform data** and check the column types. Set `month` to Date; spend, revenue, cost, rates and error metrics to Decimal Number; and counts to Whole Number where appropriate. Select **Close & Apply**.

## 2. Create measures
Open `powerbi/measures.dax`. Choose **Modeling → New measure** and paste each measure one at a time. Measures are written for the named tables above.

Optional: choose **View → Themes → Browse for themes** and select `powerbi/marketing_theme.json`.

## 3. Recommended report pages
### Page 1 — Executive overview
Use **Monthly Totals** for cards: Total Spend, Total Leads, Total Appointments, Completed Visits, Attributed Revenue, ROAS, and Contribution After Media. Add a line chart with `month` on the X-axis and spend/revenue as values. Add a month slicer.

### Page 2 — Channel performance
Use **Channel Performance** for a channel matrix/table with spend, leads, appointments, visits, CPL, cost per appointment, ROAS and contribution. Add a bar chart with channel on the axis and Channel ROAS or Channel Contribution as values.

### Page 3 — Office performance
Use **Office Performance** for a matrix by office/market with spend, leads, completed visits, revenue, ROAS, and contribution.

### Page 4 — Forecast and budget scenarios
Use **Forecast Evaluation** for MAE, RMSE and WAPE comparisons. Use **Budget Scenarios** and **Budget Allocation** for scenario comparison and channel allocation changes. Mark all optimization values as modeled estimates.

### Page 5 — Incrementality practice
Use **Experiment Summary**, **Group Comparison**, and **Market Experiment** to display treatment/control descriptives. Add a visible limitation note: assignments are fixed by market and no pre-period baseline is supplied, so this is not a robust causal estimate.

## 4. Data-model caution
These are pre-aggregated tables at different grains. **Do not create relationships among all summary tables indiscriminately**. Keep them independent for separate report pages unless you intentionally design a proper star schema. A slicer from one disconnected table will not filter a different table.

## 5. Save and publish
Save the project as `Marketing_Forecasting_Budget_Optimization.pbix`. For public sharing, publish to Power BI Service only if your account and organization's sharing policies allow it. Do not publish private or confidential data.
