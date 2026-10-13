# Power BI report build guide

## Import data
1. Install Power BI Desktop: https://powerbi.microsoft.com/desktop/
2. Select **Get data → Text/CSV**.
3. Import `data/raw_marketing_data.csv` when that file is uploaded. Rename the table to **Raw Marketing Data**.
4. In Power Query, check types: dates as Date; spend/revenue/cost as Decimal Number; counts as Whole Number.
5. From **Modeling → New measure**, paste measures in `measures.dax` one at a time.

## Recommended pages
### 1 — Executive overview
- Cards: Total Spend, Total Leads, Completed Visits, Attributed Revenue, Return On Ad Spend, Contribution After Media
- Line chart: month by Total Spend and Attributed Revenue
- Bar chart: channel by Return On Ad Spend
- Slicers: Month, Office, Channel

### 2 — Channel performance
- Table/matrix by Channel: spend, leads, appointments, visits, cost per lead, cost per appointment, ROAS, contribution
- Bar chart: contribution after media by channel

### 3 — Office performance
- Matrix by Office with spend, leads, completed visits, revenue, ROAS
- Monthly trend chart

### 4 — Forecast and budget scenarios
- Forecast evaluation table with MAE, RMSE and WAPE
- Budget scenario comparison
- Budget allocation changes by channel

### 5 — Incrementality practice
- Treatment/control comparison
- Explicitly label as descriptive only: treatment assignment is fixed by market, and no pre-period baseline is supplied.

## Modeling caution
Do not relate all summary CSV tables to raw marketing rows indiscriminately; that can double-count metrics. Begin with the raw marketing fact table for page 1. Add summary tables on separate pages or create intentional dimensions and relationships.
