# Data dictionary and grain

All data in this repository is synthetic practice data.

- `monthly_totals.csv`: 36 rows, one per month from Jan 2023 through Dec 2025; use for monthly trends and executive KPIs.
- `channel_performance.csv`: 4 rows, one per marketing channel across the full 36-month period.
- `office_performance.csv`: 10 rows, one per office across the full 36-month period.
- `budget_scenarios.csv`: 3 modeled spend scenarios at the same monthly spend level.
- `budget_allocation.csv`: baseline vs. optimized average monthly channel allocations.
- `forecast_evaluation.csv`: holdout forecast error comparison for leads and appointments.
- `experiment_summary.csv`: raw group-level summaries of treatment/control practice data.
- `group_comparison.csv`: equal-weighted market efficiency comparison by assigned group.
- `market_experiment.csv`: one row per practice market with treatment assignment and 12-month aggregate outcomes.
- `experiment_raw_data.csv`: 96 market-month practice rows for 8 markets across 12 months.

**Modeling note:** These files have different grains and are pre-aggregated. Keep the tables separate for separate report pages unless a designed model defines how they relate. Do not join them directly and sum repeated totals. The granular 1,440-row source CSV is included in the downloadable starter bundle in this conversation, but is not committed to this GitHub repository.
