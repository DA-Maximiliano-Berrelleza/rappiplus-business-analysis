# RappiPlus | Profitability, Conversion, and Retention

[Español](README.md) | English

A data analysis case study examining the performance of a subscription service.

## Business context and problem

This case examines RappiPlus, a subscription service within the Rappi ecosystem. The objective was to estimate profit after marketing expenses, identify where the conversion funnel loses the most users, measure activity after registration, and evaluate whether a new checkout interface improves conversion.

## My contribution

- **Prepared the data with Python and pandas.** Checked for duplicates, missing values, and inconsistent amounts. Combined orders, product catalog data, and marketing spend to calculate revenue, costs, and profit.
- **Analyzed user behavior with SQL in PostgreSQL.** Built a six-stage funnel tracking the same users and compared monthly cohorts. Because events were recorded at day-level precision, compared a strictly increasing date criterion with one that allowed steps on the same date.
- **Evaluated the experiment with statsmodels.** Compared purchase conversion between the control and treatment groups using a two-sided, two-proportion z-test.
- **Built a Power BI dashboard.** Presented sales and profitability metrics, revenue trends, and each product's contribution.

## Results

| Area | Finding |
| --- | --- |
| Data quality | The analysis dataset contained **24,916 orders** after addressing incomplete, inconsistent, and duplicate records. |
| Profitability | The analyzed orders generated **51.95 million in revenue** and **5.96 million in profit** after deducting the cost of goods sold and marketing expenses. |
| Conversion | **229 of 7,796 users (2.94%)** completed the sequence on strictly increasing dates. **258 (3.31%)** had a compatible sequence when steps on the same day were allowed. The largest drop-off by user count occurred between adding to cart and starting checkout. |
| Retention | Across the five cohorts analyzed, **63.12% to 65.10%** of users were active at least once between days 21 and 28 after registration. |
| A/B test | Conversion was **15.69%** in the control group and **16.29%** in the treatment group. With **p = 0.416**, there was insufficient evidence to recommend changing the interface based on an improvement in conversion. |

## Data and supporting files

The case uses CSV files containing orders, product catalog data, marketing spend, and experiment results, along with PostgreSQL tables for events, users, and activity.

- [Project notebook](./RappiPlus_Portafolio.ipynb). Includes code, queries, and aggregated tables. Recalculating the funnel and retention analysis requires authorized access to PostgreSQL.
- [Power BI report in PDF](./RappiPlus_Dashboard.pdf). Presents sales and profitability metrics.
